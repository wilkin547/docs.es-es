---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 4281c7bf5a7972d323e1e649aaef437c7ee901ff
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956263"
---
# <a name="-recurse"></a>-recurse
Compila los archivos de código fuente en todos los directorios secundarios del directorio especificado o del directorio del proyecto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Argumentos  
 `dir`  
 Opcional. El directorio en el que quiere que comience la búsqueda. Si no se especifica, la búsqueda comienza en el directorio del proyecto.  
  
 `file`  
 Necesario. Los archivos que buscará. Se admiten los caracteres comodín.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar caracteres comodín en un nombre de archivo para compilar todos los archivos coincidentes en `-recurse`el directorio del proyecto sin usar. Si no se especifica ningún nombre de archivo de salida, el compilador basa el nombre del archivo de salida en el primer archivo de entrada procesado. Normalmente es el primer archivo de la lista de archivos compilados cuando se ve en orden alfabético. Por esta razón, es mejor especificar un archivo de salida mediante la `-out` opción.  
  
> [!NOTE]
> La `-recurse` opción no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible al compilar desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El comando siguiente compila todos los archivos de Visual Basic en el directorio actual.  
  
```console
vbc *.vb  
```  
  
 El comando siguiente compila todos los archivos de Visual Basic en el `Test\ABC` directorio y los directorios situados por debajo de él y `Test.ABC.dll`, a continuación, genera.  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [-out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
