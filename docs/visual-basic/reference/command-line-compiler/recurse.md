---
description: Mas información sobre -recurse
title: -recurse
ms.date: 03/13/2018
helpviewer_keywords:
- /recurse compiler option [Visual Basic]
- -recurse compiler option [Visual Basic]
- recurse compiler option [Visual Basic]
ms.assetid: 84a0b670-33ae-44c4-a46a-b90388809317
ms.openlocfilehash: 2c0f1788c3811e24e2d51ff30e4cb2842aa0bd7a
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100475882"
---
# <a name="-recurse"></a>-recurse

Compila archivos de código fuente de todos los directorios secundarios del directorio especificado o del directorio del proyecto.  
  
## <a name="syntax"></a>Sintaxis  
  
```console  
-recurse:[dir\]file  
```  
  
## <a name="arguments"></a>Argumentos  

 `dir`  
 Opcional. El directorio en el que quiere que comience la búsqueda. Si no se especifica, la búsqueda comienza en el directorio del proyecto.  
  
 `file`  
 Obligatorio. Los archivos que buscará. Se admiten los caracteres comodín.  
  
## <a name="remarks"></a>Comentarios  

 Puede usar caracteres comodín en un nombre de archivo para compilar todos los archivos coincidentes en el directorio del proyecto sin usar `-recurse`. Si no se especifica ningún nombre de archivo de salida, el compilador basa el nombre del archivo de salida en el primer archivo de entrada procesado. Normalmente es el primer archivo de la lista de archivos compilados cuando está ordenada alfabéticamente. Por esta razón, es mejor especificar un archivo de salida mediante la opción `-out`.  
  
> [!NOTE]
> La opción `-recurse` no está disponible en el entorno de desarrollo de Visual Studio; solo está disponible cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  

 El siguiente comando compilar todos los archivos de Visual Basic del directorio actual.  
  
```console
vbc *.vb  
```  
  
 El siguiente comando compila todos los archivos de Visual Basic en el directorio `Test\ABC` y los directorios que haya por debajo y luego genera `Test.ABC.dll`.  
  
```console
vbc -target:library -out:Test.ABC.dll -recurse:Test\ABC\*.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](index.md)
- [-out (Visual Basic)](out.md)
- [Líneas de comandos de compilación de ejemplo](sample-compilation-command-lines.md)
