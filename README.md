# 📘 Aprendiendo TypeScript

Este repositorio fue creado por **Aleksei Dg** para documentar y almacenar todo lo aprendido sobre **TypeScript**, siguiendo un curso especializado.  
El objetivo es tener un espacio centralizado con notas, ejemplos de código, prácticas y fundamentos que permitan reforzar conocimientos y consultar de manera rápida cuando sea necesario.

---

## 🎯 Propósito del Repositorio

- Documentar de manera organizada lo aprendido en el curso de TypeScript.
- Crear ejemplos prácticos y pequeños proyectos que refuercen los conceptos.
- Construir una base de conocimientos propia reutilizable en futuros proyectos con **TypeScript**.

---

## 👨‍💻 ¿Qué es TypeScript?

TypeScript es un **superset de JavaScript** desarrollado por Microsoft, que agrega **tipado estático, interfaces y características avanzadas de POO (Programación Orientada a Objetos)**.  
Su principal ventaja es que permite detectar errores en tiempo de desarrollo, mejora la legibilidad y hace el código más escalable.

---

## 📚 Fundamentos Clave

A continuación, un vistazo a los temas que se cubren en este repositorio:

1. **Introducción a TypeScript**
   - Instalación y configuración.
   - Diferencias con JavaScript.
2. **Tipos básicos**
   - `string`, `number`, `boolean`, `any`, `unknown`, `void`, `null`, `undefined`.
   - Arreglos y tuplas.
   - Tipos personalizados (`type` & `interface`).
3. **Funciones**
   - Tipado de parámetros y retornos.
   - Parámetros opcionales y predeterminados.
   - Funciones flecha con tipos.
4. **Objetos e Interfaces**
   - Definición de interfaces.
   - Extensión e implementación.
5. **Clases y Programación Orientada a Objetos**
   - Clases, constructores y modificadores de acceso (`public`, `private`, `protected`).
   - Herencia y polimorfismo.
   - Propiedades `readonly` y `static`.
6. **Generics (Genéricos)**
   - Funciones genéricas.
   - Interfaces y clases genéricas.
7. **Módulos y Namespaces**
   - Importaciones y exportaciones.
   - Organización de código.
8. **Decoradores (Decorators)**
   - Decoradores de clases, métodos y propiedades.
9. **Configuración avanzada con `tsconfig.json`**
   - Compilación y opciones clave.
10. **Buenas prácticas**
    - Tipado estricto.
    - Reutilización de tipos.
    - Código limpio con TypeScript.

---

## 🗂️ Organización del Repositorio

La estructura será la siguiente:

```plaintext
LearnTypeScript/
├── src/                # Código fuente y ejemplos
│   ├── basics/         # Tipos básicos y funciones
│   ├── oop/            # Clases y POO
│   ├── generics/       # Genéricos
│   ├── modules/        # Módulos y namespaces
│   └── decorators/     # Decoradores
├── notes/              # Apuntes y documentación adicional
├── tests/              # Pruebas unitarias
├── tsconfig.json       # Configuración de TypeScript
└── README.md           # Documentación principal
```

---

## 📝 Ejemplos de Código

### 1. Tipos Básicos

```typescript
// src/basics/types.ts
let nombre: string = "Aleksei";
let edad: number = 30;
let activo: boolean = true;
let datos: any = { clave: "valor" };
let valores: number[] = [1, 2, 3];
let tupla: [string, number] = ["ID", 123];
```

### 2. Funciones Tipadas

```typescript
// src/basics/functions.ts
function sumar(a: number, b: number): number {
  return a + b;
}

const saludar = (nombre: string = "Invitado"): string => `Hola, ${nombre}`;
```

### 3. Interfaces y Objetos

```typescript
// src/basics/interfaces.ts
interface Usuario {
  id: number;
  nombre: string;
  activo?: boolean;
}

const usuario: Usuario = { id: 1, nombre: "Aleksei" };
```

### 4. Clases y POO

```typescript
// src/oop/Persona.ts
class Persona {
  readonly nombre: string;
  private edad: number;

  constructor(nombre: string, edad: number) {
    this.nombre = nombre;
    this.edad = edad;
  }

  saludar(): void {
    console.log(`Hola, soy ${this.nombre}`);
  }
}
```

### 5. Genéricos

```typescript
// src/generics/ArrayUtils.ts
function obtenerPrimerElemento<T>(arr: T[]): T | undefined {
  return arr[0];
}

const primero = obtenerPrimerElemento<string>(["a", "b", "c"]);
```

### 6. Módulos

```typescript
// src/modules/saludo.ts
export function saludar(nombre: string): string {
  return `¡Hola, ${nombre}!`;
}

// src/modules/main.ts
import { saludar } from "./saludo";
console.log(saludar("Aleksei"));
```

### 7. Decoradores

```typescript
// src/decorators/log.ts
function Log(target: any, propertyKey: string, descriptor: PropertyDescriptor) {
  const metodoOriginal = descriptor.value;
  descriptor.value = function (...args: any[]) {
    console.log(`Llamando a ${propertyKey} con argumentos:`, args);
    return metodoOriginal.apply(this, args);
  };
}

class Calculadora {
  @Log
  sumar(a: number, b: number): number {
    return a + b;
  }
}
```

---

## ⚙️ Configuración Básica de TypeScript

```json
// tsconfig.json
{
  "compilerOptions": {
    "target": "ES6",
    "module": "commonjs",
    "strict": true,
    "outDir": "./dist",
    "rootDir": "./src",
    "esModuleInterop": true
  }
}
```

---

## ✅ Buenas Prácticas

- Usa tipado estricto siempre que sea posible.
- Prefiere `interface` sobre `type` para objetos y clases.
- Mantén el código modular y reutilizable.
- Documenta tus funciones y clases.
- Utiliza pruebas unitarias para validar tu código.

---

## 🔗 Recursos Útiles

- [Documentación oficial de TypeScript](https://www.typescriptlang.org/docs/)
- [Playground interactivo de TypeScript](https://www.typescriptlang.org/play)
- [Curso gratuito de TypeScript en YouTube](https://www.youtube.com/results?search_query=typescript+curso)
- [Guía de buenas prácticas TypeScript](https://www.typescriptlang.org/docs/handbook/declaration-files/do-s-and-don-ts.html)
- [TypeScript Deep Dive (libro online)](https://basarat.gitbook.io/typescript/)

---

## 📢 Contribuciones

Si tienes sugerencias, correcciones o quieres aportar ejemplos, ¡no dudes en abrir un issue o pull request!

