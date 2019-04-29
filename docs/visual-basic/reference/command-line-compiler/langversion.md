---
title: -langversion (Visual Basic)
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: db2cb1eb107973e9ce60ecb0d669c677d4fa2c51
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61793966"
---
# <a name="-langversion-visual-basic"></a>-langversion (Visual Basic)
Hace que el compilador acepta solo la sintaxis que se incluye en la versión de idioma de Visual Basic especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-langversion:version  
```  
  
## <a name="arguments"></a>Argumentos  
 `version`  
 Obligatorio. La versión de idioma que se usará durante la compilación. Valores aceptados son `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` y `latest`.

 Cualquiera de los números enteros también pueden especificarse mediante `.0` como la versión secundaria, por ejemplo, `11.0`.

 Puede ver la lista de todos los valores posibles mediante la especificación de `-langversion:?` en la línea de comandos.  
  
## <a name="remarks"></a>Comentarios  
 El `-langversion` opción especifica la sintaxis que el compilador acepta. Por ejemplo, si especifica que la versión de lenguaje es 9.0, el compilador genera errores de sintaxis que es válida únicamente en la versión 10.0 y versiones posteriores.  
  
 Puede usar esta opción para desarrollar aplicaciones destinadas a versiones diferentes de .NET Framework. Por ejemplo, si tiene como destino .NET Framework 3.5, podría usar esta opción para asegurarse de que no usan la sintaxis de la versión 10.0 del lenguaje.  
  
 Puede establecer `-langversion` directamente utilizando la línea de comandos. Para obtener más información, consulte [Elegir una versión específica de .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version).  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `sample.vb` para Visual Basic 9.0.  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Elegir una versión específica de .NET Framework](/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
