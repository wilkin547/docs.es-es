---
title: -quiet
ms.date: 07/20/2015
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
ms.openlocfilehash: 32f82eb428c1d3bc427a10b9ca7a1a5feb9e339a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816543"
---
# <a name="-quiet"></a>-quiet
Evita que el compilador muestre código de errores y advertencias relacionados con la sintaxis.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-quiet  
```  
  
## <a name="remarks"></a>Comentarios  
 De forma predeterminada, `-quiet` no está en vigor. Cuando el compilador notifica una advertencia o error relacionados con la sintaxis, también genera la línea de código fuente. Para las aplicaciones que analizar la salida del compilador, puede ser más conveniente para el compilador genere sólo el texto del diagnóstico.  
  
 En el ejemplo siguiente, `Module1` produce un error que incluye código de origen cuando se compila sin `-quiet`.  
  
```vb  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 Resultado:  
 
```console
C:\projects\vb2.vb(3) : error BC30451: 'x' is not declared. It may be inaccessible due to its protection level.

        x()
        ~
``` 
 Compilado con `-quiet`, el compilador sólo muestra lo siguiente:  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  El `-quiet` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible solo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `T2.vb` y no se muestra código de los diagnósticos de compilador relacionados con la sintaxis:  
  
```  
vbc -quiet t2.vb  
```  
  
## <a name="see-also"></a>Vea también

- [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
