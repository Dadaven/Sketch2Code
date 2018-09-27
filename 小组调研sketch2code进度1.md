**小组调研sketch2code进度**



​      Sketch2Code 是一个基于 Web 的解决方案，使用 AI 将手绘的用户界面草图转换为可用的 HTML 代码。Sketch2Code 由微软和 Kabel、Spike Techniques 合作开发。读者可以在 GitHub 上找到与 Sketch2Code 相关的代码、解决方案开发过程和其他详细信息。

一.如何使用sketch2code

官方网址：https://sketch2code.azurewebsites.net/

1.用户将图片上传到网站上。

2.自定义视觉模型预测在图像中出现的 HTML 元素，并将它们的位置标出来。

3.手写文本识别服务读取预测元素中的文本。

4.布局算法根据预测元素的边框空间信息生成网格结构。

5.HTML 生成引擎使用上述信息来生成 HTML 代码。

二.Sketch2Code 的架构设计

Sketch2Code 使用了以下组件：  

1.微软自定义视觉模型（Custom Vision）：这个模型是基于不同的手绘稿的图象训练得出的，并标记了与常见 HTML 元素（如文本框、按钮、图像等）相关的信息。

2.微软计算机视觉服务：用于识别设计元素中的文本。

3.Azure Blob Storage：保存与 HTML 生成过程的每个步骤相关的信息，包括原始图像、预测结果、布局和分组信息等。

4.Azure Function：它作为后端入口点，通过与其他服务发生交互来协调生成过程。

5.Azure Website：用户界面前端，用户可以在这里上载设计图，并查看生成的 HTML。