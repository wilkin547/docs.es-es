---
title: /moduleassemblyname | Documentos de Microsoft
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
- moduleassemblyname compiler option [Visual Basic]
- /moduleassemblyname compiler option [Visual Basic]
- -moduleassemblyname compiler option [Visual Basic]
ms.assetid: 013a57b6-f425-4dd3-b333-512d72c42f55
caps.latest.revision: 16
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
ms.openlocfilehash: f6b042b26ad866f177158562653c91f4f7527c04
ms.lasthandoff: 03/13/2017

---
# <a name="moduleassemblyname"></a>/moduleassemblyname
Especifica el nombre del ensamblado del que este módulo formará parte.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/moduleassemblyname:assembly_name  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`assembly_name`|El nombre del ensamblado que formará parte de este módulo.|  
  
## <a name="remarks"></a>Comentarios  
 Procese el compilador la `/moduleassemblyname` opción únicamente en caso el `/target:module` se ha especificado la opción. Esto hace que el compilador crear un módulo. El módulo creado por el compilador sólo es válido para el ensamblado especificado con el `/moduleassemblyname` opción. Si coloca el módulo en un ensamblado diferente, se producirán errores de tiempo de ejecución.  
  
 El `/moduleassemblyname` opción es necesaria sólo cuando se cumple la siguiente:  
  
-   Un tipo de datos en el módulo necesita acceso a un `Friend` tipo en un ensamblado.  
  
-   El ensamblado de referencia ha concedido acceso de ensamblado de confianza al ensamblado en el que se generará el módulo.  
  
 Para obtener más información acerca de cómo crear un módulo, consulte [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md). Para obtener más información acerca de ensamblados de confianza, consulte [Friend (ensamblados)](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055).  
  
> [!NOTE]
>  El `/moduleassemblyname` opción no está disponible en el entorno de desarrollo de Visual Studio; está disponible sólo cuando se compila desde un símbolo del sistema.  
  
## <a name="see-also"></a>Vea también  
 [Cómo: compilar un ensamblado de múltiples archivos](http://msdn.microsoft.com/library/261c5583-8a76-412d-bda7-9b8ee3b131e5)   
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [/ main](../../../visual-basic/reference/command-line-compiler/main.md)   
 [/Reference (Visual Basic)](../../../visual-basic/reference/command-line-compiler/reference.md)   
 [/addmodule](../../../visual-basic/reference/command-line-compiler/addmodule.md)   
 [Ensamblados y caché Global de ensamblados](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Ensamblados de confianza](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)
