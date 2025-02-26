# 修正后的Dockerfile
FROM registry.cn-hangzhou.aliyuncs.com/mhu/aichat:v1.2

# 创建项目目录（如果基础镜像已有可省略）
RUN mkdir -p /project

# 拷贝项目文件（包含scripts目录）
COPY . /project/

# 设置脚本可执行权限
RUN chmod +x /project/scripts/start.sh

# 配置健康检查
HEALTHCHECK --interval=30s --timeout=5s \
  CMD ps aux | grep -v grep | grep start.sh || exit 1

# 容器入口配置
WORKDIR /project

# 仅作标明用
EXPOSE 9898
CMD ["sh", "-c", "/project/scripts/start.sh && tail -f /dev/null"]