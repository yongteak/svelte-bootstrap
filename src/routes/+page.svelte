<script lang="ts">
    import "../app.pcss";
    import Settings from "lucide-svelte/icons/settings";
    import Rabbit from "lucide-svelte/icons/rabbit";
    import Bird from "lucide-svelte/icons/bird";
    import Turtle from "lucide-svelte/icons/turtle";
      
    import { Button } from "$lib/components/ui/button/index.js";
    import * as Drawer from "$lib/components/ui/drawer/index.js";
    import { Input } from "$lib/components/ui/input/index.js";
    import { Textarea } from "$lib/components/ui/textarea/index.js";
    import { Label } from "$lib/components/ui/label/index.js";
    import * as Select from "$lib/components/ui/select/index.js";
  </script>
  <h1>wow</h1>
<Drawer.Root>
    <Drawer.Trigger asChild let:builder>
      <Button builders={[builder]} variant="ghost" size="icon" class="md:hidden">
        <Settings class="size-4" />
        <span class="sr-only">Settings</span>
      </Button>
    </Drawer.Trigger>
    <Drawer.Content class="max-h-[80vh]">
      <Drawer.Header>
        <Drawer.Title>Configuration</Drawer.Title>
        <Drawer.Description>
          Configure the settings for the model and messages.
        </Drawer.Description>
      </Drawer.Header>
      <form class="grid w-full items-start gap-6 overflow-auto p-4 pt-0">
        <fieldset class="grid gap-6 rounded-lg border p-4">
          <legend class="-ml-1 px-1 text-sm font-medium"> Settings </legend>
          <div class="grid gap-3">
            <Label for="model">Model</Label>
            <Select.Root>
              <Select.Trigger
                id="model"
                class="items-start [&_[data-description]]:hidden"
              >
                <Select.Value placeholder="Select a model" />
              </Select.Trigger>
              <Select.Content>
                <Select.Item value="genesis" label="Neural Genesis">
                  <div
                    class="flex items-start gap-3 text-muted-foreground"
                  >
                    <Rabbit class="size-5" />
                    <div class="grid gap-0.5">
                      <p>
                        Neural
                        <span class="font-medium text-foreground">
                          Genesis
                        </span>
                      </p>
                      <p class="text-xs" data-description>
                        Our fastest model for general use cases.
                      </p>
                    </div>
                  </div>
                </Select.Item>
                <Select.Item value="explorer" label="Neural Explorer">
                  <div
                    class="flex items-start gap-3 text-muted-foreground"
                  >
                    <Bird class="size-5" />
                    <div class="grid gap-0.5">
                      <p>
                        Neural
                        <span class="font-medium text-foreground">
                          Explorer
                        </span>
                      </p>
                      <p class="text-xs" data-description>
                        Performance and speed for efficiency.
                      </p>
                    </div>
                  </div>
                </Select.Item>
                <Select.Item value="quantum" label="Neural Quantum">
                  <div
                    class="flex items-start gap-3 text-muted-foreground"
                  >
                    <Turtle class="size-5" />
                    <div class="grid gap-0.5">
                      <p>
                        Neural
                        <span class="font-medium text-foreground">
                          Quantum
                        </span>
                      </p>
                      <p class="text-xs" data-description>
                        The most powerful model for complex
                        computations.
                      </p>
                    </div>
                  </div>
                </Select.Item>
              </Select.Content>
            </Select.Root>
          </div>
          <div class="grid gap-3">
            <Label for="temperature">Temperature</Label>
            <Input id="temperature" type="number" placeholder="0.4" />
          </div>
          <div class="grid gap-3">
            <Label for="top-p">Top P</Label>
            <Input id="top-p" type="number" placeholder="0.7" />
          </div>
          <div class="grid gap-3">
            <Label for="top-k">Top K</Label>
            <Input id="top-k" type="number" placeholder="0.0" />
          </div>
        </fieldset>
        <fieldset class="grid gap-6 rounded-lg border p-4">
          <legend class="-ml-1 px-1 text-sm font-medium"> Messages </legend>
          <div class="grid gap-3">
            <Label for="role">Role</Label>
            <Select.Root selected={{ value: "system", label: "System" }}>
              <Select.Trigger>
                <Select.Value placeholder="Select a role" />
              </Select.Trigger>
              <Select.Content>
                <Select.Item value="system">System</Select.Item>
                <Select.Item value="user">User</Select.Item>
                <Select.Item value="assistant">Assistant</Select.Item>
              </Select.Content>
            </Select.Root>
          </div>
          <div class="grid gap-3">
            <Label for="content">Content</Label>
            <Textarea id="content" placeholder="You are a..." />
          </div>
        </fieldset>
      </form>
    </Drawer.Content>
  </Drawer.Root>