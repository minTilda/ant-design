---
category: 设计模式 - 探索
type: 全局规则
order: 3
title: 空状态
skip: true
---
任何内容区域（页面、区块、组件、单数据）没有内容/数据显示给用户时，就会出现空状态。

## 设计目标

- 空状态应给予提示，帮助让用户了解空状态原因，避免产生误解与迷失。
- 给予用户推荐操作提示，帮助用户摆脱空状态。

---

## 设计原则

<div class="design-inline-cards">
  <div>
    <img src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*oFhLTpfwMP8AAAAAAAAAAABkARQnAQ" />
    <div>
      <h4>明确</h4>
      <p>通过使用清晰明了的语言、插画等形式告知用户空状态的具体原因。</p>
    </div>
  </div>
  <div>
    <img src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*rajdRoJHRXMAAAAAAAAAAABkARQnAQ" />
    <div>
      <h4>提供邀请</h4>
      <p>提供帮助文案、建议操作等解决方案，表明在下一个界面可以做什么，引导用户进行操作。</p>
    </div>
  </div>
</div>

### Do&Don’t

在表单页中组织呈现各表单项时要注意简洁表达，高效准确，避免增加用户录入信息的成本。

<img class="preview-img no-padding good" align="right" src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*k9DyRYLzjcoAAAAAAAAAAABkARQnAQ" alt="错误示范">

一个表单页中针对同一种内容类型的表单项不要使用不同的组件或表现形式，会增加用户理解成本。

<br />

<img class="preview-img no-padding good" align="right" src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*A0EBQ6eAkiwAAAAAAAAAAABkARQnAQ" alt="正确示范">
<img class="preview-img no-padding bad" align="right" src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*V56PRpofMRUAAAAAAAAAAABkARQnAQ" alt="错误示范">

表单项的标题、提示不要使用不易理解的词汇或过长，造成理解成本，如不可避免使用少见词汇，可使用帮助说明等元素辅助设计。

<br />

<img class="preview-img no-padding good" align="right" src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*EC9uR6LiI0IAAAAAAAAAAABkARQnAQ" alt="错误示范">

预填提示避免正确的废话，列如一个叫姓名的表单项输入提示是“请输入姓名”。

---

## 如何设计

表单类页面模板聚焦于提交一次表单的过程体验。按照任务的复杂度，提供四种解决问题的布局方式：

- 普通布局
- 任务拆解和编排
- 填写和预览
- 特定场景

### 普通布局

平铺所有需要填写的信息，适合内容项较少、内容项无法按照相关性分组的表单。

#### 模板 - 基础表单

<img class="preview-img no-padding" align="right" src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*c7b6TpKWl-cAAAAAAAAAAABkARQnAQ">

**什么时候用**

当需要完成一个简单快速的任务，例如输入少量信息即可完成创建。

### 任务拆解和编排

将大型、复杂任务拆解为多个部分，并按照相关性分组，减轻用户输入负担。尽管每部分内容单独处理，但最终一起完成提交。适用于大型、复杂表单。通过适当的任务分割，可以降低用户出错率。

#### 模板 - 基础分步表单

<img class="preview-img no-padding" align="right" src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*E8wRRpLbdyoAAAAAAAAAAABkARQnAQ">

**什么时候用**

将用户需要填写和确认的信息按照线性流程组织，利用步骤条告知用户完整流程和进度，常常在最后提交前让用户再次确认信息，并在流程结束给与明确的结果反馈。适用于具有明确的线性逻辑的任务。

#### 模板 - 分组表单

<img class="preview-img no-padding" align="right" src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*k6kGSLGZsT0AAAAAAAAAAABkARQnAQ">

**什么时候用**

单次任务的表单页中需要填写内容众多，且不同内容之中存在一定可分类归纳性。

#### 模板 - 可编辑列表（开发中）

**什么时候用**

适用于页面中需要添加一个或多个对象，且每个对象都需要添加或编辑多组数据的情况。

<img class="preview-img no-padding" align="right" src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*NLEeSLhLA3EAAAAAAAAAAABkARQnAQ">

动态增减：建议条目表单数 ≤3 项，并且每个输入框不需要单独的标题使用。

<img class="preview-img no-padding" align="right" src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*PvoTSbqKywEAAAAAAAAAAABkARQnAQ">

可编辑表格：建议条目表单数 2 ～ 5 项 时使用，以使得每行内容可被完整呈现。

<img class="preview-img no-padding" align="right" src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*DWlCQazb-HQAAAAAAAAAAABkARQnAQ">

折叠面板编辑：建议条目表单数在 6 ～ 8 项 时使用。

<img class="preview-img no-padding" align="right" src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*ttDGTLid8M4AAAAAAAAAAABkARQnAQ">

抽屉编辑：建议条目表单表单数 >8 项 时使用。

<img class="preview-img no-padding" align="right" src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*p_wLTJEYOBgAAAAAAAAAAABkARQnAQ">

规则树：应用于规则编辑场景。

### 特定场景模板

#### 模板 - 设置

<img class="preview-img no-padding" align="right" src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*n9zkSKrDU8MAAAAAAAAAAABkARQnAQ">

**什么时候用**

个人档案、应用配置等设置类页面，使用频率较低，一般用户操作后不会频繁修改。

**使用建议**

每个页面选择一种设置模式：

> - 即时生效模式：用户在修改选项即生效；
> - 提交生效模式：当设置项之间有关联关系，使用提交生效模式。

根据设置项数量确定是否需要分组：

> - 数量 <7 项，不建议分组；
> - 数量 7~ 15 个建议分组；
> - 数量 >15 个建议使用页签分组；

#### 模板 - 登录

<img class="preview-img no-padding" align="right" src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*ba6DR5U23nAAAAAAAAAAAABkARQnAQ">

#### 模板 - 注册

<img class="preview-img no-padding" align="right" src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*6U_gQ6MbrSYAAAAAAAAAAABkARQnAQ">

---

## 设计建议

### 前期准备

- 表单页的核心由表单项组成，设计前建议先熟悉[表单基础规则](https://next.ant.design/components/form-cn/)；
- 梳理用户当前信息录入任务中所涉及的信息类型，[并根据 Ant Design 数据录入规则](https://ant.design/docs/spec/data-entry-cn#header) 确定所使用的组件；

### 布局方式

在单个表单页中需要根据内容量进行合理地布局，以兼顾页面展示和用户效率。表单页布局可由简到繁划分为 4 个梯度，每一级梯度都兼容前一种布局方式。

#### 基础布局

<img class="preview-img no-padding" align="right" src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*lacoSZduvVQAAAAAAAAAAABkARQnAQ">

在一个区域内从上到下单列布局，引导用户纵向阅读，据[研究](https://www.uxmatters.com/mt/archives/2006/07/label-placement-in-forms.php)这是能够最高效完成任务的布局方式。

#### 弱分组

<img class="preview-img no-padding" align="right" src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*E7YuRo094e0AAAAAAAAAAABkARQnAQ">

在空间有限时，较短宽度且具有相关性的表单项可多个组合在一行中，形成分组的暗示。

<br />

<img class="preview-img no-padding good" align="right" src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*Nd_nQLmFQQwAAAAAAAAAAABkARQnAQ" alt="错误示范">

为避免和弱分组布局的阅读顺序混淆，一个区域内禁用多列表单。

#### 区域内分组

<img class="preview-img no-padding" align="right" src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*eU8dRZUTEM8AAAAAAAAAAABkARQnAQ">

当一个区域中内容较多且存在可分类归纳性时，可通过区分标题来进行区域内分组。

#### 卡片分组

<img class="preview-img no-padding" align="right" src="https://gw.alipayobjects.com/mdn/rms_08e378/afts/img/A*DoKmSYGaYtYAAAAAAAAAAABkARQnAQ">

关于使用何种布局方式的判断，和[详情页](https://next.ant.design/docs/spec/detail-page-cn#%E8%AE%BE%E8%AE%A1%E5%BB%BA%E8%AE%AE)类似，应从信息的复杂度和关联性两个维度去梳理。随后可选择相匹配的模板，进行页面快速搭建。

---

## 扩展阅读

### 会用到哪些模块或组件

- [表单](https://next.ant.design/components/form-cn/#header)
- [步骤条](https://next.ant.design/components/steps-cn/#header)

### 外部参考文章

- [Label Placement in Forms](https://www.uxmatters.com/mt/archives/2006/07/label-placement-in-forms.php)

