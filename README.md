# Este Cluster com HDFS, Yarn e Spark pode ser usado como base para testar Pipelines de ETL e Machine Learning 

# Inicializar o cluster

lembrando que trabalho com um M3 e se o seu processador é diferente, é necessario ajustar o java no dockerfile e pode ter que chamar como docker-compose e não docker compose  como esta avaixo

docker compose -f docker-compose.yml up -d --scale spark-worker-yarn=3
docker compose logs

# Testar o cluster
docker exec sil-spark-master-yarn spark-submit --master yarn --deploy-mode cluster ./examples/src/main/python/pi.py

# Derrubar o cluster
docker compose down --volumes --remove-orphans

# Spark Master
http://localhost:9091

# History Server
http://localhost:18081