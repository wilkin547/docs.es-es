---
title: -langversion
ms.date: 03/10/2018
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
ms.openlocfilehash: 72a5638a5c5364381ffd68604b0d44830d53f365
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344210"
---
# <a name="-langversion-visual-basic"></a>-langversion (Visual Basic)
Hace que el compilador acepte solo la sintaxis que se incluye en la especificación elegida del lenguaje Visual Basic.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-langversion:version  
```  
  
## <a name="arguments"></a>Argumentos  
 `version`  
 Obligatorio. La versión del lenguaje que se va a usar durante la compilación. Los valores aceptados son `9`, `10`, `11`, `12`, `14`, `15`, `15.3`, `15.5`, `default` y `latest`.

 También se puede especificar cualquiera de los números enteros mediante `.0` como la versión secundaria, por ejemplo, `11.0`.

 Puede ver la lista de todos los valores posibles si especifica `-langversion:?` en la línea de comandos.  
  
## <a name="remarks"></a>Comentarios  
 La opción `-langversion` especifica qué sintaxis acepta el compilador. Por ejemplo, si especifica que la versión del lenguaje es la 9.0, el compilador genera errores para la sintaxis que solo es válida en la versión 10.0 y posteriores.  
  
 Puede usar esta opción cuando desarrolle aplicaciones destinadas a versiones diferentes de .NET Framework. Por ejemplo, si selecciona .NET Framework 3.5 como destino, puede usar esta opción para asegurarse de que no usa la sintaxis de la versión 10.0 del lenguaje.  
  
 Solo puede establecer `-langversion` directamente con la línea de comandos. Para obtener más información, consulte [Elegir una versión específica de .NET Framework](/visualstudio/ide/visual-studio-multi-targeting-overview).  
  
## <a name="example"></a>Ejemplo  
 El código siguiente compila `sample.vb` para Visual Basic 9.0.  
  
```console  
vbc -langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [Elegir una versión específica de .NET Framework](/visualstudio/ide/visual-studio-multi-targeting-overview)
