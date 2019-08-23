---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: ca184fa130d62dc118d0de551ac58f3165064029
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964394"
---
# <a name="-noconfig"></a>-noconfig
Especifica que el compilador no debe hacer referencia automáticamente a los ensamblados de `System` .NET Framework `Microsoft.VisualBasic` usados normalmente o importar los espacios de nombres y.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-noconfig  
```  
  
## <a name="remarks"></a>Comentarios  
 La `-noconfig` opción indica al compilador que no compile con el archivo Vbc. RSP, que se encuentra en el mismo directorio que el archivo Vbc. exe. El archivo Vbc. rsp hace referencia a los ensamblados de .NET Framework usados `System` comúnmente `Microsoft.VisualBasic` e importa los espacios de nombres y. El compilador hace referencia implícitamente al ensamblado System `-nostdlib` . dll a menos que se especifique la opción. La `-nostdlib` opción indica al compilador que no compile con VBC. rsp ni haga referencia automáticamente al ensamblado System. dll.  
  
> [!NOTE]
> Siempre se hace referencia a los ensamblados mscorlib. dll y Microsoft. VisualBasic. dll.  
  
 Puede modificar el archivo Vbc. RSP para especificar opciones de compilador adicionales que deben incluirse en todas las compilaciones de VBC. exe `-noconfig` (excepto cuando se especifica la opción). Para obtener más información, consulte [@ (especificar archivo de respuesta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md).  
  
 El compilador procesa las opciones que `vbc` se pasan al comando en último lugar. Por lo tanto, cualquier opción de la línea de comandos invalida el valor de la misma opción en el archivo Vbc. rsp.  
  
> [!NOTE]
> La `-noconfig` opción no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.  
  
## <a name="see-also"></a>Vea también

- [-nostdlib (Visual Basic)](../../../visual-basic/reference/command-line-compiler/nostdlib.md)
- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [@ (especificar archivo de respuesta)](../../../visual-basic/reference/command-line-compiler/specify-response-file.md)
- [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
