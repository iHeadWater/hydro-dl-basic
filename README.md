# **hydro-dl-basic**

# **人工智能（Artificial Intelligence, AI）理论基础学习**

## 人工智能的三大学派
**（1）符号主义学派：基于数理逻辑，认为人类思维的过程可以用符号操作来描述，在给定由公理和规则组成的集合后，所有智能行为都能归结为对特定命题的判定问题。**
  * 精确逻辑：采用数理逻辑方法，对于命题可以用精确的规则进行划分。
    * 典型应用：专家系统，专家系统分为两个子系统：
      * 知识库：存储结构化信息。
      * 推理引擎：自动推理系统，用于评估知识库的当前状态，并应用相关规则进行逻辑推理，然后将新结论添加到知识库中。
      * 缺点：
        * 需要人为定义和补充规则，决定了专家系统的智能水平不会高于人类，无法解决复杂问题；
        * 基于逻辑推理，无法解决非逻辑性问题。
  * 模糊逻辑：元素可以属于多个不同的集合，元素和不同集合的关联性强弱由隶属度决定。
    * 模糊控制系统：
      * 模糊化：利用隶属函数完成输入变量的模糊化，得到模糊变量。
      * 模糊推理：通过规则器对输入进行推理，得到模糊控制变量。
      * 逆模糊：利用隶属函数去模糊化处理为精确的控制变量。
    * 一些定义：
      * 隶属度：用于表示不确定性的强弱，在概率随机性基础上加入了信息的意义和定性，是一种比随机性更加深刻的不确定性质。如35岁的人属于年轻人和中年人集合的隶属度可能为0.6和0.4。<br />
       
**（2）联结主义学派：基于神经网络，认为人类大脑的思维体系具有复杂的秉性结构，从神经元开始，进而研究神经网络模型和脑模型。**
  * 感知器（出现于20世纪60至70年代）：解决线性分类问题。
    * M-P模型（阈值加权和模型）：
      * 一个神经元接受的信号可以是起刺激作用的，也可以是起抑制作用的，其累积效果决定该神经元的状态，同时神经元的突触信号的输出是“全或无”，即仅当神经元接受的信号强度超过某个阈值时，才会由突触进行信号输出。
    * 学习算法：感知器学习算法。
      * 原理：输入连接的所有输出信号值和存储在处理单元局部内存中的参数值相互作用后得到求和累计值，输出通过激活函数进行处理。
      * 学习过程：**调整其中存储的参数值的过程。**
      * 分类：
        * 无监督学习：学习过程中，数据中输入样本的信息，但不知道输入和输出之间的关系，感知器通过学习抽取输入样本的特征或同级规律。如Hebb算法（赫布）。
        * 监督学习：学习过程中，数据是成对出现的，与输入对应的输出是已知的。通过逐步将集中的样本输入到网络中，根据输出结果和理想输出之间的差别来调整和学习感知器中存储的参数，从而使感知器的输出逐渐接近理想输出。如Delta法则（德尔塔，梯度下降）
    * 计算平台：晶体管。
    * 应用：几乎没有，因为需要收集大量的专门知识并定义庞杂的推理方案，成本高。
* 人工神经网络（Artificial Neural Network，即ANN ）（出现于20世纪80-90年代）：对生物神经网络的模仿，无法解决抑或问题。
    * 结构：
      * 输入层：接受来自网络外部的信号输入。
      * 隐藏层：对输入信号进行变换和学习，是人工神经网络强大学习和表达能力的来源。
      * 输出层：输出网络的计算结构。
    * 特点：
      * 信息是分布式存储和表示的。每个人工神经元中保存的参数值称为神经网络的长时记忆。**人工神经网络的学习过程，就是调整每个人工神经元保存的参数值的过程。**
      * 全局并行+局部操作。每个神经元的输入-输出映射具有局部性，全局并行使得可以高速并行地处理大量数据。
    * 学习算法：反向传播算法
      * 反向传播算法两个过程（反复执行这两个过程，直到一定的迭代次数或者损失函数不再下降为止）：
        * 前向传播：
          * 从输入层经隐藏层逐层处理后，传至输出层。
          * 通常网络输出与理想输出存在误差，用损失函数L（O,L）来计算实际输出和理想输出之间的误差，**网络的训练目标是最小化损失函数。**
        * 反向传播：
          * 利用损失函数计算输出层和理想输出之间的误差，并利用此误差计算输出层的直接前导层的误差，在用输出层前导层误差估计更前一层的误差。如此重复获得所有其他各层的误差估计。
          * 通过最小化每层的误差（梯度下降法）来修改每层的参数值，从而达到学习的目的。
    * 计算平台：图形处理器。
    * 应用：语音识别、图像识别、自动驾驶等。
* 深度学习（21世纪初-至今）：复杂函数
  * 特点：
    * 相比于传统人工神经网络最大的特点是网络成熟更多，利用了卷积神经网络和循环神经网络等更为复杂的结构，参数量成倍增长，使模型的表示和学习能力进一步提升。 
  * 学习算法：预训练+微调
    * 通过一个“预训练”的过程对神经网络进行逐层学习，在通过反向传播算法对整个网络进行“微调”。
  * 计算平台：分布图形处理器平台。
  * 应用：如图像、语音、自然语言处理等几乎所有人工智能领域。<br />
 
 **(3)行为主义学派：基于进化论，认为必须赋予机器自主感知和行动的能力，将重点放在语言、行为等外部信号的建模上。**
 * 进化计算算法：模拟生物种群在进化过程中的自然选择和自然遗传机制。
   * 遗传算法：模拟生物在自然环境中遗传和进化而形成的一种自适应全局优化概率搜索算法，按照与个体适应度成正比的概率决定当前群体中每个个体遗传到下一群体中的机会。
     * 三种遗传算法：
       * 选择算子：根据各个个体的适应度，按照一定的概率规则，从当前群体中选择出一些优良的个体遗传到下一代群体中。
       * 交叉算子：将群体内的各个个体随机搭配成对，对每一个个体，根据交叉概率交换它们之间的部分染色体。
       * 变异算子：对群体中的各个个体，以变异概率改变染色体上的基因值为其他的等位基因。
     * 遗传算法对群体反复执行选择、交叉、变异步骤，直到搜索群体找到目标函数的最优值或者满足收敛条件。
     * 特点：
       * 自适应概率搜索技术，增加搜索过程的随机性和灵活性。
       * 解空间的多点搜索，可并行处理，提高性能。
       * 以目标函数值作为搜索信息，不需要目标函数的导数等其他信息。
     * 一些定义：
       * 适应度函数：对问题中每个个体都能进行度量的函数。
       * 染色体：遗传算法使用固定长度的二进制符号串来表示群体中的个体。
 * 群体智能算法：对生物群体在协作和交互过程中涌现出的复杂行为进行建模。
   * 定义：指一群功能简单、具有信息处理能力、自组织能力的个体通过通信、交互、协作等手段所涌现出简单个体所不具备的复杂问题求解能力。
   * 特征：
     * 个体同质，没有中心控制节点，适用于并行计算模型；
     * 种群具有可扩展性，种群内个体数目可变；
     * 种群内部具有协作性，个体之间存在相互协作机制；
     * 种群具有临近性，个体之间交互机制的作用范围有限；
     * 种群具有自适应性，能顾根据环境变化自动调整；
     * 种群具有稳定性，某些个体故障不会影响到系统的正常工作。
   * 常见算法：
     * 蚁群算法：基于蚁群觅食行为的建模。
       * 特点:
          * 种群多样性：以随机概率选择路径。
          * 信息素更新的正反馈机制：某条路径更短，则往返时间越短，路径上信息素被更新的频率更高，路径上的信息素浓度更高。
       * 应用场景：组合优化问题，如任务调度问题、图着色问题、旅行商问题。
     * 粒子群算法：基于鸟群觅食行为的建模。
       * 可行解（鸟类）朝全局最优解（食物）移动和收敛的过程。
       * 一些定义：
          * 个体学习能力：个体记忆自身历史信息的能力。
          * 社会认知能力：感知临近个体飞行状态的能力。
       * 应用场景：对连续空间的优化求解问题。
  ## 机器学习
  学习就是系统在不断重复的工作中对本身能力的增强或者改进，使得系统在下一次执行同样任务或类似任务时，会比现在做的更好或效率更高。<br />
  机器学习是近20多年兴起的一门**多领域交叉学科，涉及概率论、统计学、逼近论、凸分析、算法复杂度理论等**多门学科。机器学习理论主要是涉及和分析一些让计算机可以**自动“学习”**的算法。<br />
  机器学习算法是一类从数据中自动分析获得规律，并利用规律对未知数据进行预测的算法。<br />
  [机器学习工作流程]（插入图片）<br />
  (1)机器学习的定义
  * 系统通过获取经验替身自身性能的过程。即系统自我改进过程。机器学习是人工智能的核心研究领域之一。
  * 机器学习研究的是如何使计算机能够模拟或实现人类的学习功能，从大量数据中发现规律、提取知识，并在实践中不断完善和增强自我。
  * 机器学习的过程就是一个对包含可能假设的空间进行搜索的过程，使得到的假设在满足先验知识和其他约束的前提下，与给定训练样本是最吻合的。
  * 机器学习就是一类能够让计算机从大量已知的以特征向量表示的训练样本中，学习到一个泛华能力强的分类器的方法。
     * 分类器好坏的衡量标准：损失函数
       * 分类问题中，损失函数定义为机器学习得到的分类器对样本的分类结果和样本真实类别的差异。
       * 回归问题中，损失函数定义为学习得到的分布与样本的真实分布之间的差别。
    * 目标：最小化损失函数。
      * 优化方法：
        * 启发式的方法：
          * 遗传算法
          * 粒子群算法
        * 基于梯度方向的算法：
          * 批量梯度下降法
          * 随机梯度下降法
          * 小批量梯度下降法
    * 一些定义：
      * 梯度：是一个向量（矢量），表示某一函数在该点处的方向导数沿着该方向取得最大值，即函数在该点处沿着该方向（此梯度的方向）变化最快，变化率最大（为该梯度的模）。
      * 过拟合问题：简单的最小化损失函数在训练样本上的值，容易造成分类器对没有见过的样本的分类正确率降低，即分类器的泛华能力不够。
      * 惩罚项：在损失函数里添加的一个衡量分类器复杂度的标准。
        * 惩罚项通常由分类器参数的各种形式表征，当分类器形式太复杂时，使得损失函数的值也会比较大。
        * 作用：使得降低分类器错误率的同时，也能将分类器的形式限制得比较简单，保证它的泛华能力。
         
  
 （2）机器学习的基本术语
 （3）监督学习
 （4）假设空间
 （5）学习方法三要素
 （6）奥卡姆剃刀定理
 （7）没有免费的午餐定理
 （8）训练误差和测试误差
 （9）过拟合与模型选择
 （10）泛华能力
  (11)生成模型和判别模型
 （12）模型性能评估
  
  ## 机器学习与人工智能的区别
  ## 机器学习和数据挖掘的关系
  ## 机器学习和统计学习的关系
  ## 大数据机器学习的特点
  ## 机器学习和深度学习的区别
  ## 深层学习和浅层学习的区别
  
  
  
  
  
  
  
  
  
  
  
  
  
  
  本repo主要是记录以深度学习、强化学习、迁移学习为重点的各类学习算法的日常积累，为xxxx.，先做一些知识铺垫，以下将从基础知识出发剖析不同算法之间的区别与联系，对各类学习算法有更加清晰的认识。

#**Part Ⅰ 基础知识 **


###人工智能（Artificial Intelligence, AI）

**人工智能**是计算机科学的一个分支，它企图了解智能的本质，并产生出一种新的能以人类智能相似的方式作出反应的智能机器，是研究、开发用于模拟、延伸和扩展人的智能的理论、方法、技术及应用系统的一门新的技术科学,包括**弱人工智能**、**强人工智能**、**超级人工智能**三种形态，目前的科研工作主要集中在弱人工智能这部分，并且已经取得了一系列的重大突破。

##机器学习（Machine Learning,ML）

**弱人工智能**是如何实现的，**智能**又从何而来呢？这主要归功于一种**实现人工智能的方法**——**机器学习**。

###机器学习定义一：**机器学习的第一类定义**是IBM提出的认知计算 (Cognitive Computing)，其目标是构建不需要显式编程的机器（计算机、软件、机器人、网站、移动应用、设备等）。

###机器学习定义二：上述定义很好，但可能有点太模糊。因此提出一个更精确的定义，**“正确提出的学习问题：如果计算机程序对于任务T的性能度量P通过经验E得到了提高，则认为此程序对经验E进行了学习。”**为了阐述清楚，我们举一个例子：在下棋程序中，经验E指的就是程序的上万次的自我联系的经验，任务T就是下棋，性能度量P指的就是在比赛过程中取胜的概率，有了性能指标后，我们就能告诉系统是否学习该经验。
**此处待插入图片**

###机器学习算法分类：上述定义为机器学习设定了清晰的目标，但是，它们没有告诉我们如何实现该目标，我们应该让定义更明确一些。这就需要**第二类定义**，这类定义描述了**机器学习算法**，以下是一些流行的定义。在每种情况下，都会为算法提供一组示例供其学习。

**- 监督式学习：**为算法提供训练数据，数据中包含每个示例的“正确答案”；例如，一个检测信用卡欺诈的监督学习算法接受一组记录的交易作为输入，对于每笔交易，训练数据都将包含一个表明它是否存在欺诈的标记。即用一部分已知分类、有标记的样本来训练机器后，让它用学到的特征，对还没有分类、无标记的样本进行分类、贴标签。多用于**分类**。

**- 无监督式学习：** 该算法在训练数据中寻找结构，比如寻找哪些示例彼此类似，并将它们分组到各个集群中。即所有的数据没有标记，类别未知，让它自己学习样本之间的相似性来进行分类。多用于**聚类**。

**- 半监督式学习：** 有两个样本集，一个有标记，一个没有标记。综合利用有类标的样本（ labeled sample）和没有类标的样本（ unlabeled sample），来生成合适的分类。

**有待继续解释”半监督式学习“**

###机器学习问题分类：我们希望在机器学习算法分类的基础上更具体一些，一种方法是通过分析机器学习任务能解决的问题类型，对任务进行细化：

**- 分类：**一种**监督学习**问题，其中要学习的答案是**有限多个可能值之一**；例如，在信用卡示例中，该算法必须学习如何在“欺诈”与“诚信”之间找到正确的答案，在仅有两个可能的值时，我们称之为二元分类问题；用于**实现分类的常用算法**包括：支持向量机 (SVM)、提升 (boosted) 决策树和袋装 (bagged) 决策树、k-最近邻、朴素贝叶斯 (Naïve Bayes)、判别分析、逻辑回归和神经网络。
 
 **-回归：**一种**监督学习**问题，其中要学习的答案是一个**连续值**。例如，可为算法提供一条房屋销售及其价格的记录，让它学习如何设定房屋价格；常用**回归算法**包括：线性模型、非线性模型、规则化、逐步回归、提升 (boosted) 和袋装 (bagged) 决策树、神经网络和自适应神经模糊学习。

**-细分（聚类）：**一种**无监督学习**问题，其中要学习的结构是一些类似示例的集群。一种**无监督学习**问题，其中要学习的结构是一些类似示例的集群。

**-网络分析：**一种**无监督学习**问题，其中要学习的结构是有关网络中的节点的重要性和作用的信息；例如，网页排名算法会分析网页及其超链接构成的网络，并寻找最重要的网页。谷歌等 Web 搜索引擎使用的就是这种算法，其他网络分析问题包括社交网络分析。

**此处待插入图片**

###机器学习工作流程及定义三：上述两个定义的问题在于，开发一个机器学习算法并不足以获得一个能学习的系统。诚然，机器学习算法与学习系统之间存在着差距。上述两个定义的问题在于，开发一个机器学习算法并不足以获得一个能学习的系统。诚然，机器学习算法与学习系统之间存在着差距。下面给出一个**机器学习工作流**，如下图所示；机器学习算法被用在工作流的“训练”步骤中，然后它的输出（一个经过训练的模型）被用在工作流的“预测”部分中。好的与差的机器算法之间的区别在于，我们在“预测”步骤中获得的预测质量。这就引出了机器学习的另一个定义：**“机器学习的目的是从训练数据中学习，以便对新的、未见过的数据做出尽可能好的预测”。**

###深度学习（Deep Learning,DL）

**深度学习是一种实现机器学习的技术。**到此，可能会有疑问？机器学习下的深度学习、监督学习、无监督学习以及半监督学习之间是什么关系呢？其实就是**分类方法不同而已**，他们之间可以**互相包含**。打个比方：一个人按性别可以分为男人和女人，而按年龄来分可以分为老人和小孩子。所以在深度学习中我们可以用到监督学习和非监督学习，而监督学习中可以用到很基础的不含神经元的算法（KNN算法），也可以用到添加了多层神经元的深度学习算法。

**有待插入深度学习、监督学习..图片表示**

**深度学习定义**深度学习是机器学习中一种基于对数据进行表征学习的算法。观测值（例如一幅图像）可以使用多种方式来表示，如每个像素强度值的向量，或者更抽象地表示一系列边、特定形状的区域等。而使用某些特定的表示方法更容易从实例中学习任务（例如人脸识别、面部表情识别）。**深度学习的好处是用非监督式或半监督式的特征学习和分层特征提取高效算法来替代手工获取特征。**

**深度神经网络**

**xxxx此处有待描述ANN、CNN、RNN的介绍**

###强化学习（Reinforcement Learning,RL）


###迁移学习（Transfer learning,TL）

**迁移学习**顾名思义就是把已学训练好的模型参数迁移到新的模型来帮助新模型训练。考虑到大部分数据或任务是存在相关性的，所以通过迁移学习我们可以将已经学到的模型参数（也可理解为模型学到的知识）通过某
种方式来分享给新模型从而加快并优化模型的学习效率不用像大多数网络那样从零学习 (Starting From Scratch)。

**迁移学习定义**迁移学习是机器学习技术的一种，其中在一个任务上训练的模型被重新利用在另一个相关的任务上。

**定义一：**迁移学习和领域自适应指的是将一个任务环境中学到的东西用来提升在另一个任务环境中模型的泛化能力。

**定义二：**迁移学习就是通过从已学习的相关任务中迁移其知识来对需要学习的新任务进行提高。

**迁移学习在深度学习中的应用**：迁移学习还与多任务学习和概念漂移等问题有关，它**并不完全是深度学习的一个研究领域**。尽管如此，由于训练深度学习模型需耗费巨大资源，包括大量的数据集，迁移学习便成了深度学习中一种很受欢迎的方法。但是，只有当从第一个任务中学到的模型特征是容易泛化的时候，迁移学习才能在深度学习中起到作用。“在迁移学习中，我们首先在基础数据集和任务上训练一个基础网络，然后将学习到的特征重新调整或者迁移到另一个目标网络上，用来训练目标任务的数据集。如果这些特征是容易泛化的，且同时适用于基本任务和目标任务，而不只是特定于基本任务，那迁移学习就能有效进行。”——深度神经网络中的特征如何迁移的？这种用于深度学习的迁移学习形式被称为**推导迁移** (Inductive Transfer)。就是通过使用合适但不完全相同的相关任务的模型，将模型的范围（模型偏差）以有利的方式缩小。

**此处有待插入图片**

**迁移学习使用方法**：们可以在自己的预测模型问题上使用迁移学习，通常有两种方法：**开发模型方法**和**预训练模型方法**。

对于**开发模型方法**，分为四步：
 
 **- 选择源任务：**必须选择一个与大量数据相关的预测模型问题，这个大量的数据需要与输入数据，输出数据和/或从输入到输出数据映射过程中学习的概念之间存在某种关系。

**- 开发源模型：**接下来，必须为这个第一项任务开发一个熟练的模型；该模型必须比原始模型更好，以确保一些特征学习已经发挥了其作用。

** - 重用模型：**然后可以将适合源任务的模型用作感兴趣的另一个任务模型的起点；这取决于所使用的建模技术，可能涉及到了全部或部分模型。

** - 调整模型：**可选项，对感兴趣任务的调整输入—输出配对数据或改进模型。

对于**预训练模型方法**，分为三步：

** - 选择源任务：**从可用的模型中选择预训练的源模型，许多研究机构会发布已经在大量的且具有挑战性的数据集上训练好的模型，在可用模型的模型池里面也能找到这些模型。

** - 重用模型：**然后可以将预训练的模型用作感兴趣的另一个任务模型的起点，这取决于所使用的建模技术，可能涉及使用全部或部分模型。

**-调整模型：**可选项，对感兴趣任务的调整输入—输出配对数据或改进模型。
 其中，第二类迁移学习方法在深度学习领域是很常见的。

#**Part Ⅱ**

接下来将介绍
 
 ** 机器学习 VS 深度学习 VS 强化学习 VS 迁移学习 VS 人工智能**
 




![输入图片描述](img-readme/QQ%E6%88%AA%E5%9B%BE20210315172022.png)


