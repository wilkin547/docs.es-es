---
title: -noconfig
ms.date: 03/13/2018
helpviewer_keywords:
- noconfig compiler option [Visual Basic]
- -noconfig compiler option [Visual Basic]
- /noconfig compiler option [Visual Basic]
ms.assetid: a7405067-bd21-4171-adf4-a126fa3ad6c3
ms.openlocfilehash: d7fc73aa24e3d2e323170f38f0f5d689f9c3abaf
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91065559"
---
# <a name="-noconfig"></a>-noconfig

Especifica que el compilador no debe hacer referencia automáticamente a los ensamblados de .NET Framework que se usan habitualmente ni importar los espacios de nombres `System` y `Microsoft.VisualBasic`.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-noconfig  
```  
  
## <a name="remarks"></a>Comentarios  

 La opción `-noconfig` indica al compilador que no compile con el archivo Vbc.rsp, que se encuentra en el mismo directorio que el archivo Vbc.exe. El archivo Vbc.rsp hace referencia a los ensamblados de .NET Framework que se usan habitualmente e importa los espacios de nombres `System` y `Microsoft.VisualBasic`. El compilador hace referencia implícitamente al ensamblado System.dll a menos que se especifique la opción `-nostdlib`. La opción `-nostdlib` indica al compilador que no compile con Vbc.rsp ni haga referencia automáticamente al ensamblado System.dll.  
  
> [!NOTE]
> Siempre se hace referencia a los ensamblados Mscorlib.dll y Microsoft.VisualBasic.dll.  
  
 El archivo Vbc.rsp se puede modificar para especificar más opciones de compilador que deben incluirse en todas las compilaciones de Vbc.exe (salvo si se especifica la opción `-noconfig`). Para obtener más información, consulte [@ (especificar archivo de respuesta)](specify-response-file.md).  
  
 El compilador procesa en último lugar las opciones que se pasan al comando `vbc`. Por lo tanto, cualquier opción de la línea de comandos reemplaza la configuración de la misma opción en el archivo Vbc.rsp.  
  
> [!NOTE]
> La opción `-noconfig` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.  
  
## <a name="see-also"></a>Vea también

- [-nostdlib (Visual Basic)](nostdlib.md)
- [Compilador de línea de comandos de Visual Basic](index.md)
- [@ (especificar archivo de respuesta)](specify-response-file.md)
- [-reference (Visual Basic)](reference.md)
