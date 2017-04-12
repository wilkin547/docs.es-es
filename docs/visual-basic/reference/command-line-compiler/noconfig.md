---
title: /noconfig | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
caps.latest.revision: 15
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 304d0e7fc787adb1d7776a2c047090ffc230fcc1
ms.lasthandoff: 03/13/2017

---
# <a name="noconfig"></a>/noconfig
Especifica que el compilador no debe automáticamente hacer referencia utilizados habitualmente [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] ensamblados o importar la `System` y `Microsoft.VisualBasic` los espacios de nombres.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/noconfig  
```  
  
## <a name="remarks"></a>Comentarios  
 El `/noconfig` opción indica al compilador que no compile con el archivo Vbc.rsp, que se encuentra en el mismo directorio que el archivo Vbc.exe. El archivo Vbc.rsp hace referencia a las que suelen usar [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)] ensamblados e importaciones de la `System` y `Microsoft.VisualBasic` los espacios de nombres. El compilador implícitamente hace referencia al ensamblado de System.dll a menos que el `/nostdlib` se especifica la opción. El `/nostdlib` opción indica al compilador que no compile con Vbc.rsp ni automáticamente hacen referencia al ensamblado de System.dll.  
  
> [!NOTE]
>  Siempre hacen referencia a los ensamblados Mscorlib.dll y Microsoft.VisualBasic.dll.  
  
 Puede modificar el archivo Vbc.rsp para especificar opciones adicionales del compilador que deben incluirse en cada compilación Vbc.exe (excepto cuando especifica la `/noconfig` opción). Para obtener más información, consulte [@ (especificar archivo de respuesta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).  
  
 El compilador procesa las opciones que se pasan a la `vbc` último comando. Por lo tanto, cualquier opción de la línea de comandos reemplaza la configuración de la misma opción en el archivo Vbc.rsp.  
  
> [!NOTE]
>  El `/noconfig` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="see-also"></a>Vea también  
 [/nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)   
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [@ (Especificar archivo de respuesta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)   
 [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
