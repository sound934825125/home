- density - 设置样式舒适/紧凑 `comfortable`、`compact`, from makeDensityProps
- `variant: 'text'` - 指定样式变体, `elevated`、`flat`、`tonal`、`outlined`、`text`、`plain`, from makeVariantProps
- color - from makeVariantProps
- rounded - 样式, 指定圆角, from makeRoundedProps
- border - from makeBorderProps
- elevation - from makeElevationProps
- `tag: div` - 指定组件以何种标签呈现, from makeTagProps
- theme - from makeThemeProps

**makeItemsProps**

- items - 通过 Props 数组指定列表项
- itemTitle - 指定 items 任意项作为 `item-title`
- itemValue - 指定 items 任意项作为 `item-value`
- itemChildren
- itemProps - 指定 items 任意项作为 `item-props`, 将传入 v-list-item 设置 props
- returnObject

**makeNestedProps**

- `selectStrategy: 'single-leaf'`
- `openStrategy: 'list'`
- opened
- selected
- mandatory

**makeDimensionProps**

设置组件尺寸

- heght
- maxHeight
- maxWidth
- minHeight
- minWidth
- width