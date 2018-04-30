---
title: 'Cómo: detectar si está instalada .NET Framework 3.5'
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-wpf
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- verifying whether.NET Framework 3.5 is installed [WPF]
- detecting .NET Framework 3.5 installation [WPF]
- detecting whether.NET Framework 3.5 is installed [WPF]
- determining whether.NET Framework 3.5 is installed [WPF]
ms.assetid: 8556a9d2-1eb8-48ef-919c-5baf22a2a9a2
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: e4999e3e1a9e402cb8848d030ab483f057428486
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/30/2018
---
# <a name="how-to-detect-whether-the-net-framework-35-is-installed"></a>Cómo: detectar si está instalada .NET Framework 3.5
Antes de que los administradores pueden implementar aplicaciones de Windows Presentation Foundation (WPF) en un sistema que tenga como destino el [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], debe confirmar primero que el [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] está presente en tiempo de ejecución. En este tema se proporciona un script escrito en HTML/JavaScript que los administradores pueden usar para determinar si la [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] está presente en un sistema.  
  
> [!NOTE]
>  Para obtener más información sobre cómo instalar, implementar y detectar el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], consulte [instalar .NET Framework para desarrolladores](../../../../docs/framework/install/guide-for-developers.md).  
  
## <a name="example"></a>Ejemplo  
 Cuando el [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] está instalado, el archivo MSI agrega ".NET CLR" y el número de versión a la cadena UserAgent. En el ejemplo siguiente se muestra un script incrustado en una página HTML sencilla. El script busca la cadena UserAgent para determinar si la [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] está instalado y muestra un mensaje de estado sobre los resultados de la búsqueda.  
  
> [!NOTE]
>  Esta secuencia de comandos está diseñada para Internet Explorer. Otros exploradores no pueden incluir información de .NET CLR en la cadena UserAgent.  
  
```  
<HTML>  
  <HEAD>  
    <TITLE>Test for the .NET Framework 3.5</TITLE>  
    <META HTTP-EQUIV="Content-Type" CONTENT="text/html; charset=utf-8" />  
    <SCRIPT LANGUAGE="JavaScript">  
    <!--  
    var dotNETRuntimeVersion = "3.5.0.0";  
  
    function window::onload()  
    {  
      if (HasRuntimeVersion(dotNETRuntimeVersion))  
      {  
        result.innerText =   
          "This machine has the correct version of the .NET Framework 3.5."  
      }   
      else  
      {  
        result.innerText =   
          "This machine does not have the correct version of the .NET Framework 3.5." +  
          " The required version is v" + dotNETRuntimeVersion + ".";  
      }  
      result.innerText += "\n\nThis machine's userAgent string is: " +   
        navigator.userAgent + ".";  
    }  
  
    //  
    // Retrieve the version from the user agent string and   
    // compare with the specified version.  
    //  
    function HasRuntimeVersion(versionToCheck)  
    {  
      var userAgentString =   
        navigator.userAgent.match(/.NET CLR [0-9.]+/g);  
  
      if (userAgentString != null)  
      {  
        var i;  
  
        for (i = 0; i < userAgentString.length; ++i)  
        {  
          if (CompareVersions(GetVersion(versionToCheck),   
            GetVersion(userAgentString[i])) <= 0)  
            return true;  
        }  
      }  
  
      return false;  
    }  
  
    //  
    // Extract the numeric part of the version string.  
    //  
    function GetVersion(versionString)  
    {  
      var numericString =   
        versionString.match(/([0-9]+)\.([0-9]+)\.([0-9]+)/i);  
      return numericString.slice(1);  
    }  
  
    //  
    // Compare the 2 version strings by converting them to numeric format.  
    //  
    function CompareVersions(version1, version2)  
    {  
      for (i = 0; i < version1.length; ++i)  
      {  
        var number1 = new Number(version1[i]);  
        var number2 = new Number(version2[i]);  
  
        if (number1 < number2)  
          return -1;  
  
        if (number1 > number2)  
          return 1;  
      }  
  
      return 0;  
    }  
  
    -->  
    </SCRIPT>  
  </HEAD>  
  
  <BODY>  
    <div id="result" />  
  </BODY>  
</HTML>  
```  
  
 Si la búsqueda de la versión de ".NET CLR" es correcta, aparece el siguiente tipo de mensaje de estado:  
  
 `This machine has the correct version of the .NET Framework 3.5.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; .NET CLR 3.5.20726; MS-RTC LM 8).`  
  
 En caso contrario, aparece el siguiente tipo de mensaje de estado:  
  
 `This machine does not have the correct version of the .NET Framework 3.5. The required version is v3.5.0.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; MS-RTC LM 8).`  
  
## <a name="see-also"></a>Vea también  
 [Detectar si .NET Framework 3.0 está instalado](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)
