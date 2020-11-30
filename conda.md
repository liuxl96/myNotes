
1. 获取版本号
+ conda --version
2. 获取(某一命令)帮助
+ conda --help
+ conda update --help
+ conda remove --help 
3. 环境管理
+ 创建 conda create --name your_env_name
+ 创建指定版本的python conda create ---name your_env_name python=3.5
+ 列举 conda env list
+ 进入 activate your_env_name
+ 退出 deactivate
+ 复制  conda create --name new_env_name --clone old_env_name
+ 删除 conda remove --name your_env_name --all
4. 包管理
+ 列举
   + 当前活跃环境下的所有包：conda list
   + 非当前活跃环境下的所有包：conda list -n your_env_name
+ 安装包 conda install xxx