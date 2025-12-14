## Vue 3 + TypeScript - Tasks Management App
A modern task management application built with Vue 3 and TypeScript, showcasing the power of composition API, reactive state management, and type-safe development. 
This project demonstrates practical implementation of Vue 3's latest features combined with TypeScript's strong typing system.

## 🚀 Features
• **Type-Safe Development** – Full TypeScript integration with Vue 3 Composition API. <br>
• **Reactive State Management** – Leveraging Vue's reactivity system with refs and computed properties. <br>
• **Component Architecture** – Modular, reusable components with typed props and emits. <br>
• **Task Filtering** – Dynamic filtering system (All, Todo, Done). <br>
• **Form Validation** – Input validation with error handling. <br>
• **Modern Build Setup** – Vite for lightning-fast development and optimized production builds. <br>

## 📚 Concepts Covered 

### Vue 3 Fundamentals
**Composition API** <br>
• `<script setup>` – Simplified component syntax <br>
• `ref()` – Reactive references for primitive values <br>
• `computed()` – Derived reactive state <br>
• Component communication – Props and emits with TypeScript <br>

**Reactive State Management** <br>
• Task state management – Adding, toggling, and removing tasks <br>
• Computed properties – Dynamic task counting and filtering <br>
• Event handling – Type-safe event emissions <br>

### TypeScript Integration
**Type System** <br>
• Interfaces – Task interface definition <br>
• Type aliases – TaskFilter union type <br>
• Generic typing – Typed refs and computed properties <br>
• Event typing – defineEmits with TypeScript <br>

**Type Safety** <br>
• Props validation – Runtime and compile-time type checking <br>
• Emit typing – Strongly typed component events <br>
• Template type inference – Full IDE support in templates <br>

### Component Patterns
**Component Structure** <br>
• TaskForm – Form component with validation <br>
• TaskList – List rendering with event delegation <br>
• FilterButton – Reusable filter button component <br>

**Data Flow** <br>
• Parent-child communication – Props down, events up <br>
• Event bubbling – Multi-level component communication <br>
• State management – Centralized task state in App component <br>

## 🏃🏻 How to Run this App
1. Clone the repository: <br>
   • `git clone https://github.com/DejvCodes/Vue-3-TS.git` <br>
   • `cd Vue-3-TS` <br>
2. Install dependencies: <br>
   • `npm install` <br>
3. Start development server: <br>
   • `npm run dev` <br>

## 💻 Tech Stack
[![My Skills](https://skillicons.dev/icons?i=vue,typescript,vite,nodejs)](https://skillicons.dev)

## 📁 Project Structure
```
├── src/
│   ├── components/           # Vue components
│   │   ├── TaskForm.vue      # Task input form with validation
│   │   ├── TaskList.vue      # Task list renderer
│   │   └── FilterButton.vue  # Filter control button
│   ├── types/                # TypeScript type definitions
│   │   └── Types.ts          # Task and filter type definitions
│   ├── App.vue               # Root component with state management
│   └── main.ts               # Application entry point
├── public/                   # Static assets
├── tsconfig.json             # TypeScript configuration
├── vite.config.ts            # Vite build configuration
├── LICENSE                   # MIT License
└── README.md                 # Project documentation
```

## 🎯 Key Features Implementation

### Task Management
```typescript
// Type-safe task interface
export interface Task {
    id: string;
    title: string;
    done: boolean;
}

// Union type for filters
export type TaskFilter = "all" | "todo" | "done";
```

### Reactive State
```typescript
// Reactive task list
const tasks = ref<Task[]>([]);

// Computed completed tasks count
const totalDone = computed(() => {
    return tasks.value.reduce((total, task) => 
        task.done ? total + 1 : total, 0);
});
```

### Type-Safe Events
```typescript
// Strongly typed event emissions
const emit = defineEmits<{
    addTask: [newTask: string]
}>();
```

## 🔐 License
[MIT License](LICENSE) 