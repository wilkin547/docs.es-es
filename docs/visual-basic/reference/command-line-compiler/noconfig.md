---
title: /noconfig
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 94d13ccf0168027f4560b980c41e2a001ff503fd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="noconfig"></a>/noconfig
Especifica que el compilador no debe automáticamente hacer referencia utilizados habitualmente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ensamblados o importar la `System` y `Microsoft.VisualBasic` los espacios de nombres.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/noconfig  
```  
  
## <a name="remarks"></a>Comentarios  
 El `/noconfig` opción indica al compilador que no compile con el archivo Vbc.rsp, que se encuentra en el mismo directorio que el archivo Vbc.exe. El archivo Vbc.rsp hace referencia utilizados habitualmente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ensamblados e importaciones el `System` y `Microsoft.VisualBasic` los espacios de nombres. El compilador hace referencia implícitamente a los del ensamblado System.dll a menos que el `/nostdlib` se especifica la opción. El `/nostdlib` opción indica al compilador que no compila con Vbc.rsp o automáticamente hacen referencia al ensamblado de System.dll.  
  
> [!NOTE]
>  Siempre hacen referencia a los ensamblados Mscorlib.dll y Microsoft.VisualBasic.dll.  
  
 Puede modificar el archivo Vbc.rsp para especificar opciones adicionales del compilador que deben incluirse en cada compilación Vbc.exe (excepto cuando se especifica la `/noconfig` opción). Para obtener más información, consulte [@ (especificar archivo de respuesta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).  
  
 El compilador procesa las opciones que se pasan a la `vbc` último comando. Por lo tanto, cualquier opción de la línea de comandos reemplaza la configuración de la misma opción en el archivo Vbc.rsp.  
  
> [!NOTE]
>  El `/noconfig` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="see-also"></a>Vea también  
 [/nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [@ (especificar archivo de respuesta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)  
 [/ Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
