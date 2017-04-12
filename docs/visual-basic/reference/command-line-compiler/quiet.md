---
title: / quiet | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /quiet
- quiet
dev_langs:
- VB
helpviewer_keywords:
- -quiet compiler option [Visual Basic]
- /quiet compiler option [Visual Basic]
- quiet compiler option [Visual Basic]
ms.assetid: 5d77fa23-4c50-4708-8535-649912b098e8
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: feafed7464248c38ec70087795a28ead8b8793f3
ms.lasthandoff: 03/13/2017

---
# <a name="quiet"></a>/quiet
Evita que el compilador muestre código de errores y advertencias relacionados con la sintaxis.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/quiet  
```  
  
## <a name="remarks"></a>Comentarios  
 De forma predeterminada, `/quiet` no está en vigor. Cuando el compilador notifica una advertencia o error relacionados con la sintaxis, también se genera la línea de código fuente. Para aplicaciones que analizan el resultado del compilador, puede ser más conveniente para el compilador generar sólo el texto del diagnóstico.  
  
 En el ejemplo siguiente, `Module1` produce un error que incluye código de origen cuando se compila sin `/quiet`.  
  
```  
Module Module1  
    Sub Main()  
        x()  
    End Sub  
End Module  
```  
  
 Resultado:  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
 `x`  
  
 `~`  
  
 Compilado con `/quiet`, el compilador sólo muestra lo siguiente:  
  
 `E:\test\t2.vb(3) : error BC30451: Name 'x' is not declared.`  
  
> [!NOTE]
>  El `/quiet` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible sólo cuando se compila desde la línea de comandos.  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `T2.vb` y no se mostrará el código de los diagnósticos de compilador relacionados con la sintaxis:  
  
```  
vbc /quiet t2.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
