# 板级配置说明 / Board Configuration

`board.h` 里用 `#if / #elif / #else` 选择 LED 引脚，必须提前定义**一个**板型宏，否则编译会在 `#error` 处中断。

`board.h` selects the LED pin with `#if / #elif / #else`. **Exactly one** board macro must be defined in advance, otherwise compilation stops at `#error`.

---

## 必须定义宏 / Required macros

| 宏 Macro | LED 引脚 Pin | 端口 Port | 时钟 Clock |
| --- | --- | --- | --- |
| `STM32G474CxU6` | `GPIO_PIN_6` | `GPIOC` | `__HAL_RCC_GPIOC_CLK_ENABLE()` |
| `STM32G474CxT6` | `GPIO_PIN_8` | `GPIOA` | `__HAL_RCC_GPIOA_CLK_ENABLE()` |

未定义任何一个时会报错 / Missing both produces:

```
#error "STM32G474CxU6 or STM32G474CxT6 need defined"
```
