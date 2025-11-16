## 综合

### 生成dcp文件

1. 将需要生成dcp的文件设置为顶层（`set as top`）
    ![](../Image/Dcp文件/file-20251116162741499.png)
2. 进入综合设置（`SYNTHESIS → Setting → More Options 输入 -mode out_of_context`）
    
    ![image.png](attachment:99574651-4a1a-4de1-9d60-32c61ea80573:image.png)
    
3. 跑综合并打开（`SYNTHESIS → Run Synthesis → Open Synthesized Design` ）
    
    ![image.png](attachment:425f6d84-fd84-427e-8493-87baf2c4adbc:image.png)
    
4. 在命令行窗口输入
    
    1. `write_checkpoint -force /proj/winkiliang/dcp_file/ebus_sds_pcs.dcp`
        
        ![image.png](attachment:d1918641-296f-44c3-9f55-26bafba493e4:image.png)
        
    2. 在命令行窗口输入`write_verilog -mode/proj/winkiliang/dcp_file/ebus_sds_pcs_sim.v`
        
        ![image.png](attachment:e4b744af-39d3-478c-ba33-bed566134456:image.png)
        
5. 得到生成的dcp文件或仿真文件
    
    ![image.png](attachment:bd9a4298-373a-45a0-8ec1-e14b564c729f:image.png)
    
6. 给dcp文件添加wrapper
    
    ![image.png](attachment:1fae3bce-f093-4790-938f-7ff8cdbe260e:image.png)
    
7. 把dcp文件以及wrapper提供给其他人
    

<aside> 💡

注：仅负责生成dcp的工程需要添加-mode out_of_context选项

</aside>

### 使用dcp文件

1. 选择添加目标dcp文件
    
    ![image.png](attachment:0ab44a9f-7a8a-439b-ad1d-195e0779f319:image.png)
    

<aside> 💡

注：dcp文件不能传输参数

</aside>

## 参考文献：

[详解vivado网表文件DCP文件的封装生成、使用与注意事项](https://blog.csdn.net/u014586651/article/details/110653530)