---
title: -langversion (Visual Basic)
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d9b91bf8efa6fabd21d257e51062dc881ab288f5
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="-langversion-visual-basic"></a>-langversion (Visual Basic)
Hace que el compilador acepte únicamente la sintaxis que se incluye en la versión de idioma de Visual Basic especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-langversion:version  
```  
  
## <a name="arguments"></a>Argumentos  
 `version`  
 Requerido. La versión de idioma que se usarán durante la compilación. Valores aceptados son `9`, `9.0`, `10`, y `10.0`.  
  
## <a name="remarks"></a>Comentarios  
 El `-langversion` opción especifica la sintaxis que el compilador acepta. Por ejemplo, si especifica que la versión de lenguaje es 9.0, el compilador genera errores de sintaxis que es válida únicamente en la versión 10.0 y versiones posteriores.  
  
 Puede usar esta opción para desarrollar aplicaciones destinadas a versiones diferentes de .NET Framework. Por ejemplo, si se establece como destino .NET Framework 3.5, podría utilizar esta opción para asegurarse de que no utilice la sintaxis de la versión de idioma 10.0.  
  
 Puede establecer `-langversion` directamente únicamente mediante la línea de comandos. Para obtener más información, consulte [Elegir una versión específica de .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `sample.vb` para Visual Basic 9.0.  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [Elegir una versión específica de .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
