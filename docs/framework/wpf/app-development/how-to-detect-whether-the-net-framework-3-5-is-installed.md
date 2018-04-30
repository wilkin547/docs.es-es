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
# <a name="how-to-detect-whether-the-net-framework-35-is-installed"></a><span data-ttu-id="e589e-102">Cómo: detectar si está instalada .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="e589e-102">How to: Detect Whether the .NET Framework 3.5 Is Installed</span></span>
<span data-ttu-id="e589e-103">Antes de que los administradores pueden implementar aplicaciones de Windows Presentation Foundation (WPF) en un sistema que tenga como destino el [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], debe confirmar primero que el [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] está presente en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e589e-103">Before administrators can deploy Windows Presentation Foundation (WPF) applications on a system that targets the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)], they must first confirm that the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] runtime is present.</span></span> <span data-ttu-id="e589e-104">En este tema se proporciona un script escrito en HTML/JavaScript que los administradores pueden usar para determinar si la [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] está presente en un sistema.</span><span class="sxs-lookup"><span data-stu-id="e589e-104">This topic provides a script written in HTML/JavaScript that administrators can use to determine whether the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is present on a system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e589e-105">Para obtener más información sobre cómo instalar, implementar y detectar el [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], consulte [instalar .NET Framework para desarrolladores](../../../../docs/framework/install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="e589e-105">For more detailed information on installing, deploying, and detecting the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)], see [Install the .NET Framework for developers](../../../../docs/framework/install/guide-for-developers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="e589e-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e589e-106">Example</span></span>  
 <span data-ttu-id="e589e-107">Cuando el [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] está instalado, el archivo MSI agrega ".NET CLR" y el número de versión a la cadena UserAgent.</span><span class="sxs-lookup"><span data-stu-id="e589e-107">When the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is installed, the MSI adds ".NET CLR" and the version number to the UserAgent string.</span></span> <span data-ttu-id="e589e-108">En el ejemplo siguiente se muestra un script incrustado en una página HTML sencilla.</span><span class="sxs-lookup"><span data-stu-id="e589e-108">The following example shows a script embedded in a simple HTML page.</span></span> <span data-ttu-id="e589e-109">El script busca la cadena UserAgent para determinar si la [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] está instalado y muestra un mensaje de estado sobre los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="e589e-109">The script searches the UserAgent string to determine whether the [!INCLUDE[net_v35_short](../../../../includes/net-v35-short-md.md)] is installed, and displays a status message on the results of the search.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e589e-110">Esta secuencia de comandos está diseñada para Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="e589e-110">This script is designed for Internet Explorer.</span></span> <span data-ttu-id="e589e-111">Otros exploradores no pueden incluir información de .NET CLR en la cadena UserAgent.</span><span class="sxs-lookup"><span data-stu-id="e589e-111">Other browsers may not include .NET CLR information in the UserAgent string.</span></span>  
  
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
  
 <span data-ttu-id="e589e-112">Si la búsqueda de la versión de ".NET CLR" es correcta, aparece el siguiente tipo de mensaje de estado:</span><span class="sxs-lookup"><span data-stu-id="e589e-112">If the search for the ".NET CLR " version is successful, the following type of status message appears:</span></span>  
  
 `This machine has the correct version of the .NET Framework 3.5.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; .NET CLR 3.5.20726; MS-RTC LM 8).`  
  
 <span data-ttu-id="e589e-113">En caso contrario, aparece el siguiente tipo de mensaje de estado:</span><span class="sxs-lookup"><span data-stu-id="e589e-113">Otherwise, the following type of status message appears:</span></span>  
  
 `This machine does not have the correct version of the .NET Framework 3.5. The required version is v3.5.0.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; MS-RTC LM 8).`  
  
## <a name="see-also"></a><span data-ttu-id="e589e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e589e-114">See Also</span></span>  
 [<span data-ttu-id="e589e-115">Detectar si .NET Framework 3.0 está instalado</span><span class="sxs-lookup"><span data-stu-id="e589e-115">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](../../../../docs/framework/wpf/app-development/how-to-detect-whether-the-net-framework-3-0-is-installed.md)
