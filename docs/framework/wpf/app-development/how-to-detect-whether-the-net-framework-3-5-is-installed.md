---
title: Procedimiento Detectar si está instalado .NET Framework 3.5
ms.date: 03/30/2017
helpviewer_keywords:
- verifying whether.NET Framework 3.5 is installed [WPF]
- detecting .NET Framework 3.5 installation [WPF]
- detecting whether.NET Framework 3.5 is installed [WPF]
- determining whether.NET Framework 3.5 is installed [WPF]
ms.assetid: 8556a9d2-1eb8-48ef-919c-5baf22a2a9a2
ms.openlocfilehash: 69dfa0eb8d9ad9b780d258a874d255484f270cfe
ms.sourcegitcommit: d8ebe0ee198f5d38387a80ba50f395386779334f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/05/2019
ms.locfileid: "66690439"
---
# <a name="how-to-detect-whether-the-net-framework-35-is-installed"></a><span data-ttu-id="604c8-102">Procedimiento Detectar si está instalado .NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="604c8-102">How to: Detect Whether the .NET Framework 3.5 Is Installed</span></span>
<span data-ttu-id="604c8-103">Antes de que los administradores pueden implementar aplicaciones de Windows Presentation Foundation (WPF) en un sistema que tiene como destino .NET Framework 3.5, debe confirmar primero que el tiempo de ejecución de .NET Framework 3.5 está presente.</span><span class="sxs-lookup"><span data-stu-id="604c8-103">Before administrators can deploy Windows Presentation Foundation (WPF) applications on a system that targets the .NET Framework 3.5, they must first confirm that the .NET Framework 3.5 runtime is present.</span></span> <span data-ttu-id="604c8-104">Este tema proporciona un script escrito en HTML/JavaScript que los administradores pueden usar para determinar si está presente en un sistema de .NET Framework 3.5.</span><span class="sxs-lookup"><span data-stu-id="604c8-104">This topic provides a script written in HTML/JavaScript that administrators can use to determine whether the .NET Framework 3.5 is present on a system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="604c8-105">Para obtener más información acerca de cómo instalar, implementar y detectar .NET Framework, vea [instalar .NET Framework para desarrolladores](../../install/guide-for-developers.md).</span><span class="sxs-lookup"><span data-stu-id="604c8-105">For more detailed information on installing, deploying, and detecting the .NET Framework, see [Install the .NET Framework for developers](../../install/guide-for-developers.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="604c8-106">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="604c8-106">Example</span></span>  
 <span data-ttu-id="604c8-107">Cuando se instala .NET Framework 3.5, el archivo MSI agrega ".NET CLR" y el número de versión a la cadena UserAgent.</span><span class="sxs-lookup"><span data-stu-id="604c8-107">When the .NET Framework 3.5 is installed, the MSI adds ".NET CLR" and the version number to the UserAgent string.</span></span> <span data-ttu-id="604c8-108">El ejemplo siguiente muestra un script incrustado en una página HTML sencilla.</span><span class="sxs-lookup"><span data-stu-id="604c8-108">The following example shows a script embedded in a simple HTML page.</span></span> <span data-ttu-id="604c8-109">El script busca la cadena UserAgent para determinar si .NET Framework 3.5 está instalado y muestra un mensaje de estado sobre los resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="604c8-109">The script searches the UserAgent string to determine whether the .NET Framework 3.5 is installed, and displays a status message on the results of the search.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="604c8-110">Este script está diseñado para Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="604c8-110">This script is designed for Internet Explorer.</span></span> <span data-ttu-id="604c8-111">Otros exploradores pueden no incluir información de CLR de .NET en la cadena UserAgent.</span><span class="sxs-lookup"><span data-stu-id="604c8-111">Other browsers may not include .NET CLR information in the UserAgent string.</span></span>  
  
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
  
 <span data-ttu-id="604c8-112">Si la búsqueda de la versión de ".NET CLR" se realiza correctamente, aparece el siguiente tipo de mensaje de estado:</span><span class="sxs-lookup"><span data-stu-id="604c8-112">If the search for the ".NET CLR " version is successful, the following type of status message appears:</span></span>  
  
 `This machine has the correct version of the .NET Framework 3.5.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; .NET CLR 3.5.20726; MS-RTC LM 8).`  
  
 <span data-ttu-id="604c8-113">En caso contrario, aparece el siguiente tipo de mensaje de estado:</span><span class="sxs-lookup"><span data-stu-id="604c8-113">Otherwise, the following type of status message appears:</span></span>  
  
 `This machine does not have the correct version of the .NET Framework 3.5. The required version is v3.5.0.0.`  
  
 `This machine's userAgent string is: Mozilla/4.0 (compatible; MSIE 7.0; Windows NT 6.0; SLCC1; .NET CLR 2.0.50727; .NET CLR 1.1.4322; InfoPath.2; .NET CLR 3.0.590; MS-RTC LM 8).`  
  
## <a name="see-also"></a><span data-ttu-id="604c8-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="604c8-114">See also</span></span>

- [<span data-ttu-id="604c8-115">Detectar si .NET Framework 3.0 está instalado</span><span class="sxs-lookup"><span data-stu-id="604c8-115">Detect Whether the .NET Framework 3.0 Is Installed</span></span>](how-to-detect-whether-the-net-framework-3-0-is-installed.md)
