
```sh
tail -f /dev/null
# 创建容器
docker run --name aiwechat-min -itd -v ${PWD}:/aichat --network=host -w /aichat aiwechat:v1.1  python3 /aichat/app.py

# 查看容器日志
docker logs aiwechat-min
```