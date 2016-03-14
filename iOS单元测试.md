## iOS单元测试：
##### by 崔春健

#### 一、什么是单元测试？

 1、最小可测单元

 2、不是为了发现bug，是为了提高开发效率，为了我们的代码健康可持续发展


#### 二、单元测试的优缺点

##### 1⃣️优点：

 1、好的单元测试就是一份上好的文档，而且比文档更容易被程序员接受。

 2、开发人员修改代码不再畏首畏尾，提高开发者的信心

 3、单元测试能保证在加入新功能或修改旧功能时代码的正确性

 4、单元测试保证在整个开发流程中代码都会被测试，更容易及早发现问题，降低风险。对于项目管理来说，使软件的开发流程更容易掌控。

##### 2⃣️缺点：

 1、单元测试不能减少研发的代码量，反而会花费很多精力在编写单元测试上，增加了开发成本，而且对开发人员的要求也会更高
 另外个人觉得，单元测试对于很小的项目意义不大；对于项目周期较长，需求比较复杂的中性或大型项目，单测将意义重大


#### 三、测试用例的来源

 1、需求和详细设计文档

 2、bug fix


#### 四、单元测试由谁写

 1、最好是开发者本人

 2、对于新人，可以由老师傅来写单元测试，用于指导新人开发


#### 五、如何写单元测试

 1、iOS单元测试的结构是这样的，



 2、每一个Test Case的写法有三个步骤：①Mock对象，准备测试数据。②调用要测试的目标API。③验证输出和行为是否正确

 测试普通文件消息收发:

 ```Objective-C
 - (void)testSendFileMessage {

     // ①Mock对象，准备测试数据
     BDIMFileMessage *fileMessage = [[BDIMFileMessage alloc] init];

    BDIMFileMessageContent *fileContent = [[BDIMFileMessageContent alloc] init];
     fileContent.fileName = @"bd_logo1.png";
     fileContent.filePath = deskTopPath;

 	fileMessage.comnFile = fileContent;
 	fileMessage.addresserName = @"tester";
    fileMessage.extra = @"file_extra";

     // ②调用要测试的目标API
     [self.conversation sendMessage:fileMessage];

     // ③验证输出和行为是否正确
     expect([_imMessage isKindOfClass:[BDIMFileMessage class]]).will.beTruthy();
 }
 ```
 3、Application Tests

 	.	$(BUILT_PRODUCTS_DIR)/<app_name>.app/<app_name>
 	.	$(BUNDLE_LOADER)

#### 六、代码的可测性

 * 类之间要松耦合
 * 被测试的函数需要产生可测量的结果
 * 被测试的函数要遵循单一职责
 * 展示和业务逻辑要分开
 * 记得重构，不断提高代码的可测性


#### 七、最佳实践

 * 每个功能类都应提供单元测试，且每一个测试类，只依赖于其要测试的受测类。使用伪造对象避免对其他类的依赖，保证一个测试类只关注一个被测类，当测试不通过时，就能迅速的定位到是谁发生了错误，而不会受到其他类的干扰；使用伪造环境避免其他环境的干扰，保证case在任何环境下都能输出同样的测试结果

 * 一个单测方法只测试一个功能点，并且不依赖其他测试用例的结果作为输入，保证case的原子性。if-else这种分支的情况最好分成两个case来测试

 * 单元测试通过数据的变化来做输出结果的验证

 * 应对所有暴露的属性和方法提供测试（包含回调方法），私有方法则不必。因为对外接口应该会调用到所有的私有方法，而且私有方法相对公有方法来说发生变动的可能性大很多，会造成不必要的修改测试代码的成本。如果非要测试私有方法，可以通过KVC、子类化和类别来实现

 * TDD，测试驱动开发的妙处即在于，它以需求为引领，通过测试的形式，来指导开发者进行软件的设计与架构，并编写出最为精炼的代码，使得测试用例运行通过。经过适当的重构之后，测试用例与产品代码可达到较为健康的状态。

 * 第三方的框架有很多，OCUnit、[GHUnit](https://github.com/gh-unit/gh-unit.git)、[Expecta](https://github.com/specta/expecta.git)、[OCMock](https://github.com/erikdoe/ocmock.git)，目前我使用的OCUnit + Expecta


#### 八、衡量标准

 1、代码覆盖率

 2、Case的成功率
