# 英语单词学习应用 - 架构说明

## 📋 目录结构

```
englist-learn/
├── index.html                          # 主应用文件
├── vocabulary.json                      # JSON格式的词汇数据
├── middle-school-vocabulary.js         # 初中词汇数据（已配置）
├── high-school-vocabulary.js          # 高中词汇数据（待添加）
├── college-vocabulary.js              # 大学词汇数据（待添加）
├── graduate-vocabulary.js             # 考研词汇数据（待添加）
└── ARCHITECTURE.md                     # 本文档
```

## 🎯 扩展新词汇表的步骤

### 步骤 1：准备词汇数据文件

将你的词汇数据转换为 JavaScript 文件，例如创建 `high-school-vocabulary.js`：

```javascript
const highSchoolVocabulary = [
  {
    id: "unique_id_1",
    word: "advanced",
    pronunciation: "/ədˈvɑːnst/",
    partOfSpeech: "adj.",
    meaning: "高级的；先进的",
    unit: "Unit 1",
    grade: "高中一年级上册",
  },
  // ... 更多单词
];
```

### 步骤 2：在 HTML 中引入数据文件

在 `index.html` 的 `<head>` 部分添加：

```html
<script src="./high-school-vocabulary.js"></script>
```

### 步骤 3：更新词汇表配置

在 `index.html` 中修改 `VOCABULARY_SETS` 配置：

```javascript
const VOCABULARY_SETS = [
  {
    label: "📚 初中词汇",
    value: "middle-school",
    dataVar: "vocabulary", // 对应 middle-school-vocabulary.js 中的变量名
  },
  {
    label: "📖 高中词汇",
    value: "high-school",
    dataVar: "highSchoolVocabulary", // 对应 high-school-vocabulary.js 中的变量名
  },
  {
    label: "🎓 大学词汇",
    value: "college",
    dataVar: "collegeVocabulary", // 对应 college-vocabulary.js 中的变量名
  },
  {
    label: "📝 考研词汇",
    value: "graduate",
    dataVar: "graduateVocabulary", // 对应 graduate-vocabulary.js 中的变量名
  },
];
```

## 🔧 核心架构

### 1. 词汇表管理系统

- **词汇表配置**：`VOCABULARY_SETS` 数组管理所有词汇表
- **当前词汇表**：`currentVocabularySet` 存储当前选择的词汇表
- **动态加载**：根据选择自动加载对应的数据源

### 2. 状态存储系统

每个词汇表都有独立的状态存储：

```javascript
// localStorage 键名格式
wordMastery_middle - school; // 初中词汇状态
wordMastery_high - school; // 高中词汇状态
wordMastery_college; // 大学词汇状态
wordMastery_graduate; // 考研词汇状态
```

### 3. 数据加载流程

1. 用户选择词汇表
2. 调用 `switchVocabularySet()`
3. 清空当前状态
4. 加载新词汇表数据（`loadVocabulary()`）
5. 加载新词汇表的状态（`loadWordMastery()`）

## 📝 数据结构规范

### 词汇数据对象结构

```javascript
{
  "id": "唯一标识符",
  "word": "单词",
  "pronunciation": "音标",
  "partOfSpeech": "词性",
  "meaning": "中文含义",
  "unit": "所属单元（可选）",
  "grade": "所属年级（可选）"
}
```

### 状态存储结构

```javascript
{
  "word_id_1": 0,    // 不会
  "word_id_2": 50,   // 模糊
  "word_id_3": 100,  // 掌握
  // 默认不会的单词不会存储在 localStorage 中
}
```

## 🎨 界面功能

### 词汇表选择器

- 位置：页面右上角
- 功能：切换不同的词汇表
- 默认：初中词汇

### 掌握程度筛选

- 全部：显示所有单词
- 不会：显示未标记和标记为"不会"的单词（默认状态）
- 模糊：显示标记为"模糊"的单词
- 掌握：显示标记为"掌握"的单词

### 统计信息

- 不会（红色）：未标记 + 标记为"不会"
- 模糊（黄色）：标记为"模糊"
- 掌握（绿色）：标记为"掌握"

## 🚀 扩展示例

### 添加高中词汇表

1. **创建数据文件** `high-school-vocabulary.js`：

```javascript
const highSchoolVocabulary = [
  { id: "hs1", word: "advanced", pronunciation: "音标", meaning: "含义", ... },
  // ... 更多数据
];
```

2. **在 index.html 中添加引用**：

```html
<script src="./high-school-vocabulary.js"></script>
```

3. **更新配置**（已完成，只需确保 dataVar 正确）

4. **完成！** 用户可以在界面上切换到"高中词汇"

## 💡 设计优势

- ✅ **模块化**：每个词汇表独立文件
- ✅ **可扩展**：轻松添加新词汇表
- ✅ **状态隔离**：不同词汇表状态互不干扰
- ✅ **数据持久化**：使用 localStorage 独立存储
- ✅ **用户友好**：一键切换，自动加载状态
