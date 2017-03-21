---
title: 'No se puede emitir el ensamblado: &lt;mensaje de error&gt; | Documentos de Microsoft'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30145
- bc30145
dev_langs:
- VB
helpviewer_keywords:
- BC30145
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: 11
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: dac4b133882c043f9c84e936bad2e36f35fc4c33
ms.lasthandoff: 03/13/2017

---
# <a name="unable-to-emit-assembly-lterror-messagegt"></a>No se puede emitir el ensamblado: &lt;mensaje de error&gt;
El compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] llama a Assembly Linker (Al.exe, también denominado Alink) para generar un ensamblado con un manifiesto; el vinculador informa de un error en la fase de emisión de la creación del ensamblado.  
  
 **Id. de error:** BC30145  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Examine el mensaje de error citado y consulte el tema [Al.exe herramienta errores y advertencias](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) para obtener más información y consejos.  
  
2.  Intente firmar el ensamblado manualmente, mediante la [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex) o [Sn.exe (herramienta de nombre seguro)](https://msdn.microsoft.com/library/k5b5tt23).  
  
3.  Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.  
  
### <a name="to-sign-the-assembly-manually"></a>Para firmar el ensamblado manualmente  
  
1.  Utilice la [Sn.exe (herramienta de nombre seguro)](https://msdn.microsoft.com/library/k5b5tt23) para crear un archivo de par de claves pública y privada.  
  
     Este archivo tiene la extensión .snk.  
  
2.  Elimine la referencia COM que está provocando el error en el proyecto.  
  
3.  Desde las ventanas **iniciar** menú, seleccione **programas**, seleccione **Microsoft Visual Studio 2008**, seleccione **Visual Studio Tools**y, a continuación, haga clic en **símbolo del sistema de Visual Studio 2008**.  
  
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
  
6.  En [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)], agregue una referencia de ensamblado de .NET al archivo que acaba de crear.  
  
## <a name="see-also"></a>Vea también  
 [Al.exe (Assembly Linker)](https://msdn.microsoft.com/library/c405shex)   
 [Advertencias y errores de la herramienta Al.exe](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)   
 [Sn.exe (herramienta de nombre seguro)](https://msdn.microsoft.com/library/k5b5tt23)   
 [Cómo: Crear un par de claves privada y pública](http://msdn.microsoft.com/library/05026813-f3bd-4d7c-9e0b-fc588eb3d114)   
 [Hable con nosotros](https://docs.microsoft.com/visualstudio/ide/talk-to-us)
