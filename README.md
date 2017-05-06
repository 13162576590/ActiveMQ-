# ActiveMQ-
ActiveMQ的使用代码样例（异步邮件发送）

1.edu-demo-mqconsumer

#SMTP服务配置
mail.host=smtp.qq.com
mail.port=25
mail.username=824291336@qq.com
mail.password=bmllsyyrlwyjbbgc  #qq邮箱授权码
mail.smtp.auth=true
mail.smtp.timeout=30000
mail.default.from=824291336@qq.com
mail.smtp.starttls.enable = true


<!-- Spring提供的发送电子邮件的高级抽象类 -->
<bean id="mailSender" class="org.springframework.mail.javamail.JavaMailSenderImpl">
	<property name="host" value="${mail.host}" />
	<property name="username" value="${mail.username}" />
	<property name="password" value="${mail.password}" />
	<property name="defaultEncoding" value="UTF-8"></property>
	<property name="javaMailProperties">
		<props>
			<prop key="mail.smtp.auth">${mail.smtp.auth}</prop>
			<prop key="mail.smtp.timeout">${mail.smtp.timeout}</prop>
			<!-- 必须 -->
            <prop key="mail.smtp.starttls.enable">${mail.smtp.starttls.enable}</prop>  
        </props>
	</property>
</bean>