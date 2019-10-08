---
title: -moduleassemblyname
ms.date: 03/13/2018
helpviewer_keywords:
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
ms.openlocfilehash: 5b26e36346858d95526f5d5ce7d4645bea1dbe05
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005482"
---
# <a name="-moduleassemblyname"></a>-moduleassemblyname
Especifica el nombre del ensamblado del que este módulo formará parte.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`assembly_name`|Nombre del ensamblado del que formará parte este módulo.|  
  
## <a name="remarks"></a>Comentarios  
 El compilador procesa la opción `-moduleassemblyname` solo si se ha especificado la opción `-target:module`. Esto hace que el compilador cree un módulo. El módulo creado por el compilador solo es válido para el ensamblado especificado con la opción `-moduleassemblyname`. Si coloca el módulo en otro ensamblado, se producirán errores en tiempo de ejecución.  
  
 La opción `-moduleassemblyname` solo es necesaria cuando se cumplen las condiciones siguientes:  
  
- Un tipo de datos del módulo necesita acceso a un tipo `Friend` en un ensamblado al que se hace referencia.  
  
- El ensamblado al que se hace referencia ha concedido acceso de ensamblado de confianza al ensamblado en el que se va a compilar el módulo.  
  
 Para obtener más información sobre cómo crear un módulo, vea [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md). Para obtener más información sobre los ensamblados de confianza, vea [ensamblados de confianza](../../../standard/assembly/friend.md).  
  
> [!NOTE]
> La opción `-moduleassemblyname` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde un símbolo del sistema.  
  
## <a name="see-also"></a>Vea también

- [Cómo: Compilar un ensamblado de varios archivos](../../../framework/app-domains/build-multifile-assembly.md)
- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-Target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)
- [-main](../../../visual-basic/reference/command-line-compiler/main.md)
- [-Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)
- [-addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)
- [Ensamblados de .NET](../../../standard/assembly/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Ensamblados de confianza](../../../standard/assembly/friend.md)
