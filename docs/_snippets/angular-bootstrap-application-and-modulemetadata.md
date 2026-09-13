```ts filename="YourComponent.stories.ts" renderer="angular" language="ts" tabTitle="CSF 3"
import { type Meta, type StoryObj, applicationConfig, moduleMetadata } from '@storybook/angular';

import { provideHttpClient } from '@angular/common/http';
import { CommonModule } from '@angular/common';

import { YourComponent } from './your.component';

const meta: Meta<YourComponent> = {
  component: YourComponent,
  decorators: [
    // Passed to bootstrapApplication when the story renders
    applicationConfig({
      providers: [provideHttpClient()],
    }),
    // NgModule-style metadata for the story component tree
    moduleMetadata({
      imports: [CommonModule],
      declarations: [],
      providers: [],
    }),
  ],
};
export default meta;
type Story = StoryObj<YourComponent>;

export const Base: Story = {};
```

```ts filename="YourComponent.stories.ts" renderer="angular" language="ts" tabTitle="CSF Next 🧪"
import { applicationConfig, moduleMetadata } from '@storybook/angular';
import preview from '../.storybook/preview';

import { provideHttpClient } from '@angular/common/http';
import { CommonModule } from '@angular/common';

import { YourComponent } from './your.component';

const meta = preview.meta({
  component: YourComponent,
  decorators: [
    applicationConfig({
      providers: [provideHttpClient()],
    }),
    moduleMetadata({
      imports: [CommonModule],
      declarations: [],
      providers: [],
    }),
  ],
});

export const Base = meta.story();
```
