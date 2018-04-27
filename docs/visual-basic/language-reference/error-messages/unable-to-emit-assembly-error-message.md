---
title: 'No se puede emitir el ensamblado: &lt;mensaje de error&gt;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 59288ba7b4cec34cd2266d66aa931e92598e819a
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/27/2018
---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a>No se puede emitir el ensamblado: &lt;mensaje de error&gt;
El compilador de Visual Basic llama a Assembly Linker (Al.exe, también denominado Alink) para generar un ensamblado con un manifiesto y el vinculador informa de un error en la fase de emisión de creación del ensamblado.  
  
 **Id. de error:** BC30145  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Examine el mensaje de error citado y consulte el tema [Al.exe](../../../framework/tools/al-exe-assembly-linker.md). Para obtener una explicación y consejos.  
  
2.  Intente firmar el ensamblado manualmente, mediante la [Al.exe](../../../framework/tools/al-exe-assembly-linker.md) o [Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md).  
  
3.  Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.  
  
### <a name="to-sign-the-assembly-manually"></a>Para firmar el ensamblado manualmente  
  
1.  Use el [Sn.exe (herramienta de nombre seguro)][Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md)) para crear un archivo de par de claves pública y privada.  
  
     Este archivo tiene la extensión .snk.  
  
2.  Elimine la referencia COM que está provocando el error en el proyecto.  
  
3.  Desde las ventanas **iniciar** menú, elija **programas**, seleccione **Microsoft Visual Studio 2008**, seleccione **Visual Studio Tools**, y a continuación, haga clic en **símbolo del sistema de Visual Studio 2008**.  
  
4.  Vaya al directorio en el que quiera colocar el contenedor de ensamblado.  
  
5.  Escriba el siguiente código.  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     A continuación mostramos un ejemplo del código que se podría especificar.  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     Incluya comillas dobles (") si especifica una ruta de acceso o archivo que contiene espacios.  
  
6.  En Visual Studio, agregue una referencia de ensamblado .NET al archivo que acaba de crear.  
  
## <a name="see-also"></a>Vea también  
 
 [Al.exe](../../../framework/tools/al-exe-assembly-linker.md).  
 [Sn.exe (herramienta de nombre seguro)] [Sn.exe (herramienta de nombre seguro)](../../../framework/tools/sn-exe-strong-name-tool.md))  
 [Cómo: Crear un par de claves pública y privada](../../../framework/app-domains/how-to-create-a-public-private-key-pair.md)  
 [Hable con nosotros](/visualstudio/ide/talk-to-us)
