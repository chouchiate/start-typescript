## **start-typescript-project**

### **Install Typescript**

```bash
$ npm i typescript --save-dev
```

### **Init Typescript Project**
```bash
$ npx tsc --init
```

### **My tsconfig preferences for Nodejs backend**

```json
"compilerOptions": {
  "incremental": true,
  "target": "es2018",
    "module": "commonjs",
    "allowJs": true, 
    "declaration": true,
    "sourceMap": true,
    "outDir": "dist", /* Redirect output structure to the directory. */
    "tsBuildInfoFile": "./build/build.log",               /* Specify file to store incremental compilation information */
    "baseUrl": ".",   
    "paths": {
      "*": ["node_modules/*"],
      "types/*": ["src/types/*"],
      "utils/*": ["src/utils/*"],
    },
    "typeRoots": [
      "src/types/@types/*",
      "@types",
      "node_modules/@types"      
    ],
    "allowSyntheticDefaultImports": true,
    "esModuleInterop": true,
    "forceConsistentCasingInFileNames": true
},
"files": [

],
"include": [
  "src/**/*.ts"
],
"exclude": [
  "node_modules",
],
  

```

### **Tsconfig for React frontend**
```json
{
  "compilerOptions": {
    "baseUrl": "src",
    "target": "es5",
    "lib": [
      "dom",
      "dom.iterable",
      "esnext"
    ],
    "allowJs": true,
    "skipLibCheck": true,
    "esModuleInterop": true,
    "allowSyntheticDefaultImports": true,
    "strict": true,
    "forceConsistentCasingInFileNames": true,
    "noFallthroughCasesInSwitch": true,
    "module": "esnext",
    "moduleResolution": "node",
    "resolveJsonModule": true,
    "isolatedModules": true,
    "noEmit": true,
    "inlineSourceMap": true,
    "jsx": "react-jsx",
  },
  "include": [
    "src"
  ]
}

```

### **Eslint**
```js
module.exports = {
  env: {
    browser: true,
    es2021: true,
    jest: true,
  },
  extends: [
    // instead of using airbnb, use airbnb-typescript with TS project
    'airbnb-typescript',
    'plugin:react/recommended',
    'plugin:react-hooks/recommended',
  ],
  parser: '@typescript-eslint/parser',
  parserOptions: {
    ecmaFeatures: {
      jsx: true,
    },
    ecmaVersion: 12,
    sourceType: 'module',

    // add this line if using 'airbnb-typescript'
    project: './tsconfig.json',
  },
  plugins: ['react', 'react-hooks', '@typescript-eslint'],
  settings: {
    // 避免出現 Unable to resolve path to module
    'import/resolver': {
      node: {
        paths: ['src'], // absolute import
        extensions: ['.js', '.jsx', '.ts', '.tsx'],
      },
    },
  },
  rules: {
    // avoid JSX not allowed in files with extension '.tsx'
    'react/jsx-filename-extension': [1, { extensions: ['.tsx', '.ts'] }],

    // avoid 'React' was used before it was defined
    'import/extensions': [
      'error',
      'ignorePackages',
      {
        js: 'never',
        jsx: 'never',
        ts: 'never',
        tsx: 'never',
      },
    ],

    // avoid 'React' was used before it was defined error
    'no-use-before-define': 'off',
    '@typescript-eslint/no-use-before-define': ['error'],

    // must use default export
    'import/prefer-default-export': 'off',

    // check Hook rule
    'react-hooks/rules-of-hooks': 'error',
    // check effect dependency
    'react-hooks/exhaustive-deps': 'warn',

    'react/no-children-prop': 'warn',
  },
};

```

### **Add source entry**
* create project_dir/src/index.ts
* write some code
* tsc --watch to compile
```typescript
const world = 'world';

export function hello(world: string = 'world'): string {
  return `Hello ${world}! `;
}
```

### **Configure Tslint**
```bash
  $ npm i tslint --save-dev
  $ npx tslint --init
```


## **!!GET READY TO CODE!!**

