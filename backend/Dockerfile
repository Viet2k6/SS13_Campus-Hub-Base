# Base image JRE 21 Alpine tối ưu kích thước và hiệu năng
FROM eclipse-temurin:21-jre-alpine

WORKDIR /app

# Tạo non-root user nhằm tuân thủ best practice về an toàn
RUN addgroup -S appgroup && adduser -S appuser -G appgroup

# Copy file jar đã build
COPY build/libs/*.jar app.jar

# Phân quyền cho người dùng non-root
RUN chown -R appuser:appgroup /app

USER appuser

EXPOSE 8080

ENTRYPOINT ["java", "-jar", "app.jar"]
