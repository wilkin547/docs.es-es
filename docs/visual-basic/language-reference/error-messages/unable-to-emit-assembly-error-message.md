---
title: "No se puede emitir el ensamblado: &lt;mensaje de error&gt; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc30145"
  - "bc30145"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30145"
ms.assetid: 2e7eb2b9-eda6-4bdb-95cc-72c7f0be7528
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# No se puede emitir el ensamblado: &lt;mensaje de error&gt;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

El compilador de [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] llama a Assembly Linker \(Al.exe, también denominado Alink\) para generar un ensamblado con un manifiesto; el vinculador informa de un error en la fase de emisión de la creación del ensamblado.  
  
 **Identificador del error:** BC30145  
  
### Para corregir este error  
  
1.  Estudie el mensaje de error citado y consulte el tema [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/es-es/7f125d49-0a03-47a6-9ba9-d61a679a7d4b) para ver una explicación más detallada y consejos.  
  
2.  Intente firmar el ensamblado manualmente, ya sea mediante [Al.exe \(Assembly Linker\)](../Topic/Al.exe%20\(Assembly%20Linker\).md) o con la [Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md).  
  
3.  Si el error persiste, reúna información sobre las circunstancias y notifíquelo a los Servicios de soporte técnico de Microsoft.  
  
### Para firmar el ensamblado manualmente  
  
1.  Use la [Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md) para crear un archivo de par de claves pública y privada.  
  
     Este archivo tiene la extensión .snk.  
  
2.  Elimine la referencia COM que está provocando el error en el proyecto.  
  
3.  En el menú **Inicio** de Windows, seleccione **Programas**, **Microsoft Visual Studio 2008** y **Visual Studio Tools** y, luego, haga clic en **Símbolo del sistema de Visual Studio 2008**.  
  
4.  Vaya al directorio en el que quiera colocar el contenedor de ensamblado.  
  
5.  Escriba el siguiente código.  
  
    ```  
    tlbimp <path to COM reference file> /out:<output assembly name> /keyfile:<path to .snk file>  
    ```  
  
     A continuación mostramos un ejemplo del código que se podría especificar.  
  
    ```  
    tlbimp c:\windows\system32\msi.dll /out:Interop.WindowsInstaller.dll /keyfile:"c:\documents and settings\mykey.snk"  
    ```  
  
     Incluya comillas dobles \("\) si especifica una ruta de acceso o archivo que contiene espacios.  
  
6.  En [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs-md.md)], agregue una referencia de ensamblado de .NET al archivo que acaba de crear.  
  
## Vea también  
 [Al.exe \(Assembly Linker\)](../Topic/Al.exe%20\(Assembly%20Linker\).md)   
 [Al.exe Tool Errors and Warnings](http://msdn.microsoft.com/es-es/7f125d49-0a03-47a6-9ba9-d61a679a7d4b)   
 [Sn.exe \(Strong Name Tool\)](../Topic/Sn.exe%20\(Strong%20Name%20Tool\).md)   
 [Cómo: Crear un par de claves privada y pública](../Topic/How%20to:%20Create%20a%20Public-Private%20Key%20Pair.md)   
 [Hable con nosotros](/visual-studio/ide/talk-to-us)