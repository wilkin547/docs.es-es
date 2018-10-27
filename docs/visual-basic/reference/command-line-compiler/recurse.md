---
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 1edb648ec574c0052b7b8314f4ada710c8b0fe01
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50183339"
---
# <a name="-recurse"></a>-recurse
Compila los archivos de código fuente de todos los subdirectorios del directorio especificado o el directorio del proyecto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Argumentos  
 `dir`  
 Opcional. El directorio en el que quiere que comience la búsqueda. Si no se especifica, la búsqueda comienza en el directorio del proyecto.  
  
 `file`  
 Requerido. Los archivos que buscará. Se admiten los caracteres comodín.  
  
## <a name="remarks"></a>Comentarios  
 Puede usar caracteres comodín en un nombre de archivo para compilar todos los archivos coincidentes en el directorio del proyecto sin usar `-recurse`. Si no se especifica ningún nombre de archivo de salida, el compilador utilizará el nombre de archivo de salida en el primer archivo de entrada. Esto suele ser el primer archivo en la lista de archivos compilados ordenada alfabéticamente. Por este motivo, es mejor especificar un archivo de salida mediante la `-out` opción.  
  
> [!NOTE]
>  El `-recurse` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El comando siguiente compila todos los archivos de Visual Basic en el directorio actual.  
  
```console
vbc *.vb  
```  
  
 El comando siguiente compila todos los archivos de Visual Basic en el `Test\ABC` directory y los directorios por debajo de él y, a continuación, genera `Test.ABC.dll`.  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [-out (Visual Basic)](../../../visual-basic/reference/command-line-compiler/out.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
