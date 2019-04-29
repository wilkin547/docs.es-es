---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: 44bc619c489fdff36f0b595f7d8934689b859adb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789030"
---
# <a name="-noconfig"></a>-noconfig
Especifica que el compilador no debe automáticamente hacer referencia utilizados habitualmente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ensamblados o importar la `System` y `Microsoft.VisualBasic` espacios de nombres.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a>Comentarios  
 El `-noconfig` opción indica al compilador que no compile con el archivo Vbc.rsp, que se encuentra en el mismo directorio que el archivo Vbc.exe. El archivo Vbc.rsp hace referencia a la frecuente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ensamblados y las importaciones del `System` y `Microsoft.VisualBasic` espacios de nombres. El compilador hace referencia implícitamente a los del ensamblado System.dll a menos que el `-nostdlib` se especifica la opción. El `-nostdlib` opción indica al compilador que no compila con vbc.rsp o referencia al ensamblado System.dll de automáticamente.  
  
> [!NOTE]
>  Los ensamblados de Mscorlib.dll y Microsoft.VisualBasic.dll siempre se hace referencia.  
  
 Puede modificar el archivo Vbc.rsp para especificar opciones de compiladores adicionales que deben incluirse en cada compilación Vbc.exe (excepto cuando se especifica la `-noconfig` opción). Para obtener más información, consulte [@ (especificar archivo de respuesta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).  
  
 El compilador procesa las opciones que se pasan a la `vbc` comando por última vez. Por lo tanto, cualquier opción de la línea de comandos reemplaza la configuración de la misma opción en el archivo Vbc.rsp.  
  
> [!NOTE]
>  El `-noconfig` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.  
  
## <a name="see-also"></a>Vea también

- [-nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [@ (especificar archivo de respuesta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [-referencia (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
