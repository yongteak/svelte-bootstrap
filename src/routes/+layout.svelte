<script lang="ts">
  import "../app.pcss";
  import Triangle from "lucide-svelte/icons/triangle";
  import Bot from "lucide-svelte/icons/bot";
  import SquareTerminal from "lucide-svelte/icons/square-terminal";
  import CodeXML from "lucide-svelte/icons/code-xml";
  import Settings2 from "lucide-svelte/icons/settings-2";
  import LifeBuoy from "lucide-svelte/icons/life-buoy";
  import Book from "lucide-svelte/icons/book";
  import SquareUser from "lucide-svelte/icons/square-user";
  import Settings from "lucide-svelte/icons/settings";
  import Rabbit from "lucide-svelte/icons/rabbit";
  import Bird from "lucide-svelte/icons/bird";
  import Turtle from "lucide-svelte/icons/turtle";
  import Share from "lucide-svelte/icons/share";
  import Paperclip from "lucide-svelte/icons/paperclip";
  import Mic from "lucide-svelte/icons/mic";
  import CornerDownLeft from "lucide-svelte/icons/corner-down-left";

  import { Badge } from "$lib/components/ui/badge/index.js";
  import { Button } from "$lib/components/ui/button/index.js";
  import * as Tooltip from "$lib/components/ui/tooltip/index.js";
  import * as Drawer from "$lib/components/ui/drawer/index.js";
  import { Input } from "$lib/components/ui/input/index.js";
  import { Textarea } from "$lib/components/ui/textarea/index.js";
  import { Label } from "$lib/components/ui/label/index.js";
  import * as Select from "$lib/components/ui/select/index.js";
</script>

<div class="grid h-screen w-full pl-[53px]">
  <aside class="inset-y fixed left-0 z-20 flex h-full flex-col border-r">
    <div class="border-b p-2">
      <Button variant="outline" size="icon" aria-label="Home">
        <Triangle class="size-5 fill-foreground" />
      </Button>
    </div>
    <nav class="grid gap-1 p-2">
      <Tooltip.Root>
        <Tooltip.Trigger asChild let:builder>
          <Button
            variant="ghost"
            size="icon"
            class="rounded-lg bg-muted"
            aria-label="Playground"
            builders={[builder]}
          >
            <SquareTerminal class="size-5" />
          </Button>
        </Tooltip.Trigger>
        <Tooltip.Content side="right" sideOffset={5}>Playground</Tooltip.Content>
      </Tooltip.Root>
      <Tooltip.Root>
        <Tooltip.Trigger asChild let:builder>
          <Button
            variant="ghost"
            size="icon"
            class="rounded-lg"
            aria-label="Models"
            builders={[builder]}
          >
            <Bot class="size-5" />
          </Button>
        </Tooltip.Trigger>
        <Tooltip.Content side="right" sideOffset={5}>Models</Tooltip.Content>
      </Tooltip.Root>
      <Tooltip.Root>
        <Tooltip.Trigger asChild let:builder>
          <Button
            variant="ghost"
            size="icon"
            class="rounded-lg"
            aria-label="API"
            builders={[builder]}
          >
            <CodeXML class="size-5" />
          </Button>
        </Tooltip.Trigger>
        <Tooltip.Content side="right" sideOffset={5}>API</Tooltip.Content>
      </Tooltip.Root>
      <Tooltip.Root>
        <Tooltip.Trigger asChild let:builder>
          <Button
            variant="ghost"
            size="icon"
            class="rounded-lg"
            aria-label="Documentation"
            builders={[builder]}
          >
            <Book class="size-5" />
          </Button>
        </Tooltip.Trigger>
        <Tooltip.Content side="right" sideOffset={5}>Documentation</Tooltip.Content>
      </Tooltip.Root>
      <Tooltip.Root>
        <Tooltip.Trigger asChild let:builder>
          <Button
            variant="ghost"
            size="icon"
            class="rounded-lg"
            aria-label="Settings"
            builders={[builder]}
          >
            <Settings2 class="size-5" />
          </Button>
        </Tooltip.Trigger>
        <Tooltip.Content side="right" sideOffset={5}>Settings@</Tooltip.Content>
      </Tooltip.Root>
    </nav>
    <nav class="mt-auto grid gap-1 p-2">
      <Tooltip.Root>
        <Tooltip.Trigger asChild let:builder>
          <Button
            variant="ghost"
            size="icon"
            class="mt-auto rounded-lg"
            aria-label="Help"
            builders={[builder]}
          >
            <LifeBuoy class="size-5" />
          </Button>
        </Tooltip.Trigger>
        <Tooltip.Content side="right" sideOffset={5}>Help</Tooltip.Content>
      </Tooltip.Root>
      <Tooltip.Root>
        <Tooltip.Trigger asChild let:builder>
          <Button
            variant="ghost"
            size="icon"
            class="mt-auto rounded-lg"
            aria-label="Account"
            builders={[builder]}
          >
            <SquareUser class="size-5" />
          </Button>
        </Tooltip.Trigger>
        <Tooltip.Content side="right" sideOffset={5}>Account</Tooltip.Content>
      </Tooltip.Root>
    </nav>
  </aside>
  <div class="flex flex-col">
    <header
      class="sticky top-0 z-10 flex h-[57px] items-center gap-1 border-b bg-background px-4"
    >
      <h1 class="text-xl font-semibold">Playground</h1>
    </header>
    <!-- <main class="flex-1 overflow-y-auto"> -->
      <slot />
    <!-- </main> -->
  </div>
</div>

<!-- </main>

<footer class="fixed bottom-0 left-0 w-full bg-gray-800 text-white text-center p-4">
  © 2023 Your Company
</footer> -->