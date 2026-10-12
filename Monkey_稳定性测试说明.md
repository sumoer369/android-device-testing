# Monkey 稳定性测试说明

## 1. 测试目的
验证系统应用在随机高频操作下的稳定性，监控 ANR（应用无响应）与 Crash（崩溃）的发生频率。

## 2. 测试环境
- **测试设备**：iQOO Z10 Turbo (OriginOS 4)
- **连接工具**：ADB (Android Debug Bridge)
- **测试工具**：Monkey（Android SDK 内置）

## 3. 测试命令
计划执行 100 次随机点击，每次间隔 500ms 以模拟真实用户操作：
`adb shell monkey -p com.android.settings --throttle 500 -v 100`

*注：由于当前PC环境尚未配置ADB系统环境变量，且为保证手机日常使用不受影响，测试计划已于本地文档记录，准备在后续测试环境中执行。*

## 4. 监控指标
- **Events injected**：随机事件注入总数
- **ANR / Crash**：运行期间是否出现应用无响应或闪退
- **Monkey finished**：是否正常结束（无异常捕获）

## 5. 预期结论
系统应用在 100 次随机点击下运行稳定，未触发崩溃或 ANR 异常。
