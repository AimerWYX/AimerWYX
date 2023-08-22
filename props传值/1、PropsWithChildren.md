## PropsWithChildren

> 在 React Native 中，PropsWithChildren 不是 React Native 特有的概念，而是来自于 React 库本身的 TypeScript 类型。PropsWithChildren 是一种类型定义，用于表示一个组件的 props 对象，并明确表示该组件可以接受子组件作为子元素。

> 在 React 和 React Native 中，组件的 props 是用来传递信息和配置给组件的机制。而 PropsWithChildren 类型是一种用于 TypeScript 语法的类型，用于表示一个具有子组件的组件的 props。它表明该组件可以接受一个或多个子元素作为其内容。

```typescript
import React, { PropsWithChildren } from "react";
import { View, Text } from "react-native";

type CardProps = PropsWithChildren<{ title: string }>;
// type CardProps = { title: string } & PropsWithChildren<{}>;

const Card = ({ title, children }: CardProps) => {
  return (
    <View style={{ borderWidth: 1, padding: 10 }}>
      <Text>{title}</Text>
      {children}
    </View>
  );
};

export const App = () => {
  return (
    <Card title="Card 标题">
      <Text>这是 Card 的内容。</Text>
    </Card>
  );
};
```

在上面的示例中，Card 组件接受一个 title 属性作为字符串，并且使用 PropsWithChildren 类型表示该组件可以接受子元素作为 children。App 组件使用 Card 组件，并在其内部传递了一个 Text 组件作为子元素。

总结来说，PropsWithChildren 是一种 TypeScript 类型，用于表示一个组件的 props 中可以包含子元素（children）。这使得开发者在使用 TypeScript 时能够更明确地定义组件的接口。
