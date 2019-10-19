eclipse maven 依赖打包

<build>
		<pluginManagement></pluginManagement>
		<plugins>
			<plugin>
				<groupId>org.apache.maven.plugins</groupId>
				<artifactId>maven-assembly-plugin</artifactId>
				<configuration>
					<descriptorRefs>
						<descriptorRef>jar-with-dependencies</descriptorRef>
					</descriptorRefs>
					<archive>
						<manifest>
							<mainClass>com.rf.cloud.annuity.DpQuartzApplication</mainClass>
						</manifest>
					</archive>
				</configuration>
				<executions>  
                  <execution>  
                    <id>make-assembly</id>  
                    <phase>package</phase>   
                    <goals>  
                        <goal>single</goal>  
                    </goals>  
                  </execution>  
                </executions>
			</plugin>
		</plugins>
	</build>

网上找了很多种，最后一段可以行的通； 

3、右键项目——>run as 选择maven install，打包完成后可以看到项目的target目录下多了两个jar包；

其中第一个jar包不包含项目依赖包，第二个项目包含依赖包（在com下）

然后运行jar包。命令 java  -jar  test-kafka-1.0.0-SNAPSHOT-jar-with-dependencies.jar    ，如果是运行jar包下的main方法 需要制定 命令是：java -cp   test-kafka-1.0.0-SNAPSHOT-jar-with-dependencies.jar  com.test..kafka.Producer(执行main方法class文件路径)


<plugin>
		      <artifactId>maven-assembly-plugin</artifactId>
		      <configuration>
		        <archive>
		          <manifest>
		            <mainClass>com.rf.cloud.annuity.DpQuartzApplication</mainClass>
		          </manifest>
		        </archive>
		        <descriptorRefs>
		          <descriptorRef>jar-with-dependencies</descriptorRef>
		        </descriptorRefs>
		      </configuration>
		      <executions>  
                  <execution>  
                    <id>make-assembly</id>  
                    <phase>package</phase>   
                    <goals>  
                        <goal>single</goal>  
                    </goals>  
                  </execution>  
                </executions>
</plugin>





​      <plugin>
​                <groupId>org.springframework.boot</groupId>
​                <artifactId>spring-boot-maven-plugin</artifactId>
​                <version>1.4.2.RELEASE</version>
​                <configuration>
​                    <fork>true</fork>
​                    <mainClass>com.rf.cloud.annuity.DpQuartzApplication</mainClass>
​                </configuration>
​                <executions>
​                    <execution>
​                        <goals>
​                            <goal>repackage</goal>
​                        </goals>
​                    </execution>
​                </executions>
​        </plugin>