---
title: -quiet
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- -quiet
- quiet
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
caps.latest.revision: ''
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a0ed08e013f088f512ae915daa9aeb2fa6b249b0
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2018
---
# <a name="-quiet"></a>-quiet
Evita que el compilador muestre código de errores y advertencias relacionados con la sintaxis.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
-quiet  
```  
  
## <a name="remarks"></a>Comentarios  
 De forma predeterminada, `-quiet` no está en vigor. Cuando el compilador notifica una advertencia o error relacionados con la sintaxis, también se genera la línea de código fuente. Para las aplicaciones que analizar la salida del compilador, puede ser más conveniente para el compilador que genere sólo el texto del diagnóstico.  
  
 En el ejemplo siguiente, `Module1` genera un error que incluye código de origen cuando se compila sin `-quiet`.  
  
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
 Compilado con `-quiet`, el compilador genera solo lo siguiente:  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  El `-quiet` opción no está disponible en el entorno de desarrollo de Visual Studio, que está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `T2.vb` y no se mostrarán el código de diagnóstico de compilador relacionados con la sintaxis:  
  
```  
vbc -quiet t2.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
