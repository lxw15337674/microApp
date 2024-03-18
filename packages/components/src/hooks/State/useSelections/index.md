# useSelections

常见联动 Checkbox 逻辑封装，支持多选，单选，全选逻辑，还提供了是否选择，是否全选，是否半选的状态。


## 代码演示
<demo src="./demo/demo.vue" title="基本用法" desc="使用el-checkbox"></demo>

<demo src="./demo/demo2.vue" title="多选框组" desc="使用el-checkbox-group"></demo>

## API

```typescript
const [state, { toggle, set, setTrue, setFalse }] = useBoolean(
  defaultValue?: boolean,
);
```

## Params

| 参数         | 说明                     | 类型      | 默认值  |
| ------------ | ------------------------ | --------- | ------- |
| defaultValue | 可选项，传入默认的状态值 | `boolean` | `false` |

## Result

| 参数    | 说明     | 类型                     |
| ------- | -------- | ------------------------ |
| state   | 状态值   | `Readonly<Ref<boolean>>` |
| actions | 操作集合 | `Actions`                |

## Actions

| 参数     | 说明         | 类型                       |
| -------- | ------------ | -------------------------- |
| toggle   | 切换 state   | `() => void`               |
| set      | 设置 state   | `(value: boolean) => void` |
| setTrue  | 设置为 true  | `() => void`               |
| setFalse | 设置为 false | `() => void`               |