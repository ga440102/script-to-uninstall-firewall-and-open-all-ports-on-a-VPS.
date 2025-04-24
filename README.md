#!/bin/bash

# 卸载防火墙相关包
echo "卸载防火墙及相关包..."
sudo apt purge -y iptables-persistent

# 重置 iptables 规则，允许所有流量
echo "重置防火墙规则..."
sudo iptables -P INPUT ACCEPT
sudo iptables -P FORWARD ACCEPT
sudo iptables -P OUTPUT ACCEPT
sudo iptables -F

# 保存更改
echo "防火墙已卸载，端口已开放。"

