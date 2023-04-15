# 安装过程参考
https://wxyhgk.com/article%2Fubuntu-slurm

# 测试邮件系统
echo "邮件内容" | s-nail -s "邮件主题" 你的qq邮箱地址

# 常用命令
squeue -u johnsmith #johnsmith是用户名  查看队列情况  
sudo systemctl restart slurmctld ##restart


# 测试 sbatch 服务

vim test.slurm

"""
#!/bin/bash  
#SBATCH -J dog  
#SBATCH -p master  
#SBATCH -N 1  
#SBATCH -n 1  
#SBATCH --mail-user=你的qq邮箱  
#SBATCH --mail-type=ALL  

sleep 5   
whoami  
"""

# example
"

#!/bin/bash  
#SBATCH -J test_slurm
#SBATCH -p user-NF8480M5  
#SBATCH -N 1  
#SBATCH -n 1  
#SBATCH --cpus-per-task=12  
#SBATCH --output=%x.%j.out     
#SBATCH --error=%x.%j.out      
#SBATCH --mail-user=479321347@qq.com  
#SBATCH --mail-type=ALL  


conda activate kneaddata  
kneaddata -i1 /data/zhiyu/est/raw/SRR1927149_1.fastq.gz -i2 /data/zhiyu/est/raw/SRR1927149_2.fastq.gz -db /data/zhiyu/db/hosts/human_db -o /data/zhiyu/da_tools/cleaned/
conda deactivate



"
# 集群管理
学习中https://yuhldr.github.io/posts/bfa79f01.html
