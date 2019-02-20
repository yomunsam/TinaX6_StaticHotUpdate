# TinaX6_StaticHotUpdate
Tina X6 Framework静态热更新 服务端模板

## Json配置说明

``` json
{
    "versions":[ //版本数组根目录
        {  //每个数组item，为一个母包版本数据
            "base_version":1, 
            "upgrade_type":"max", //max:只下载版本号最新的补丁包; each: 依次下载该母包配置下的所有补丁包; cease:该母包版本已不提供补丁包，需要下载新的母包
            "download_type":"", //下载方式： default:客户端直接根据url下载; webpage: 客户端不处理下载，调用浏览器之类的工具打开网页。 该处理方式进针对母包下载。补丁包只能由客户端下载。
            "webpage_url":"xxxxx", //如果“download_type”为“webpage”，则打开此处配置的网页
            "base_pack_url":"xxx", //如果“download_type”为“default”，则以此地址下载母包安装文件
            "packages":[    //该母包版本对应的补丁包数据
                {
                    "version":1, //补丁版本号（每个母包之间版本号不互相干涉）
                    "md5":"xxxxxx", //补丁包的校验文件
                    "url":"xxxx", //下载路径
                    "size":100, //补丁包的体积：单位应该为KiB
                }
            ]
        }
    ]
}

```
