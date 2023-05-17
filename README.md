## Structure Overall

```
tree --gitignore -L 5 -F --dirsfirst
./
├── public/
├── src/
│   ├── common/
│   │   ├── confirm/
│   │   │   ├── components/
│   │   │   │   ├── ConfirmDialog.stories.tsx
│   │   │   │   └── ConfirmDialog.tsx
│   │   │   ├── hooks/
│   │   │   │   ├── useConfirm.test.ts
│   │   │   │   └── useConfirm.ts
│   │   │   └── index.ts
│   │   └── translate/
│   │       ├── hooks/
│   │       │   ├── useTranslate.test.ts
│   │       │   └── useTranslate.ts
│   │       └── index.ts
│   ├── components/
│   │   ├── button/
│   │   │   ├── Button.stories.tsx
│   │   │   ├── Button.tsx
│   │   │   ├── IconButton.stories.tsx
│   │   │   ├── IconButton.tsx
│   │   │   └── index.ts
│   │   └── text-field/
│   ├── modules/
│   │   ├── app/
│   │   │   ├── components/
│   │   │   │   ├── AppHeader.stories.tsx
│   │   │   │   └── AppHeader.tsx
│   │   │   └── index.ts
│   │   ├── project/
│   │   │   ├── components/
│   │   │   │   ├── ProjectEditDialog.stories.tsx
│   │   │   │   ├── ProjectEditDialog.tsx
│   │   │   │   ├── ProjectTable.stories.tsx
│   │   │   │   └── ProjectTable.tsx
│   │   │   ├── hooks/
│   │   │   │   ├── useProjectCostCalculate.test.ts
│   │   │   │   └── useProjectCostCalculate.ts
│   │   │   ├── pages/
│   │   │   │   ├── ProjectDetail.stories.tsx
│   │   │   │   ├── ProjectDetail.tsx
│   │   │   │   ├── ProjectIndex.stories.tsx
│   │   │   │   └── ProjectIndex.tsx
│   │   │   └── index.ts
│   │   └── project-search/
│   │       ├── components/
│   │       │   ├── ProjectSearch.stories.tsx
│   │       │   └── ProjectSearch.tsx
│   │       ├── hooks/
│   │       │   ├── useProjectSearch.fake.ts
│   │       │   ├── useProjectSearch.test.ts
│   │       │   └── useProjectSearch.ts
│   │       └── index.ts
│   ├── pages/
│   │   └── projects/
│   │       ├── [id].tsx
│   │       └── index.tsx
│   ├── utils/
│   │   ├── array/
│   │   │   ├── sum.test.ts
│   │   │   └── sum.ts
│   │   └── date/
│   ├── App.tsx
│   ├── main.tsx
│   └── vite-env.d.ts
├── README.md
├── index.html
├── package.json
├── pnpm-lock.yaml
├── tsconfig.json
├── tsconfig.node.json
└── vite.config.ts
```

## Rules

### all codes (, except utils and pages) should have `index.ts` that controls "what is exported"

Easily uniform private modules and public.

### functionality should be colocated, not categorized by technologies

Easily modify functionality.

### components should have stories for storybook

Easily develop and confirm UI.

### hooks and utils should have test file for unit testing

As they are widely used in an application, it makes easy to refactor app without regression.

## Key Directories

### common

Includes functionality used across the app. It is colocated by the functionality, not care about what is exported (some may have components and hooks, but others may have only hooks).

### components

Includes ui components used across the app. Consider them like native HTML elements installed in the app.

### modules

Includes modules that consists of application. Consider them like micro-app developed by their team.
Can use common, components, utils, as they are developed by such as base team.

### pages

Includes route specific components. This directory determines client side URL.

### utils

Includes low level utilities. Consider them like native JS API installed in the app.
