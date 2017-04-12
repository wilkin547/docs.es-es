---
title: /langversion (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- /langversion compiler option [Visual Basic]
- langversion compiler option [Visual Basic]
- -langversion compiler option [Visual Basic]
ms.assetid: 59b7b0c8-2dde-4e9b-94e7-0237f7e0bafb
caps.latest.revision: 8
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
ms.openlocfilehash: 9970df0c9babc368210169fae0490b423d77f40d
ms.lasthandoff: 03/13/2017

---
# <a name="langversion-visual-basic"></a>/langversion (Visual Basic)
Hace que el compilador acepte únicamente la sintaxis que se incluye en la versión de idioma de Visual Basic especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/langversion:version  
```  
  
## <a name="arguments"></a>Argumentos  
 `version`  
 Obligatorio. La versión de idioma que se usará durante la compilación. Valores aceptados son `9`, `9.0`, `10`, y `10.0`.  
  
## <a name="remarks"></a>Comentarios  
 El `/langversion` opción especifica la sintaxis que acepta el compilador. Por ejemplo, si especifica que la versión de lenguaje es 9.0, el compilador genera errores de sintaxis que es válida en la versión 10.0 y versiones posteriores.  
  
 Puede utilizar esta opción al desarrollar aplicaciones destinadas a versiones diferentes de .NET Framework. Por ejemplo, si su objetivo es .NET Framework 3.5, podría utilizar esta opción para asegurarse de que no utilice la sintaxis de la versión 10.0.  
  
 Puede establecer `/langversion` directamente utilizando la línea de comandos. Para obtener más información, consulte [Elegir una versión específica de .NET Framework](https://docs.microsoft.com/visualstudio/ide/targeting-a-specific-dotnet-framework-version).  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `sample.vb` para Visual Basic 9.0.  
  
```  
vbc /langversion:9.0 sample.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Elegir una versión específica de .NET Framework](https://docs.microsoft.com/visualstudio/ide/targeting-a-specific-dotnet-framework-version)
