---
title: /RootNamespace | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /rootnamespace
- rootnamespace
dev_langs:
- VB
helpviewer_keywords:
- /rootnamespace compiler option [Visual Basic]
- -rootnamespace compiler option [Visual Basic]
- rootnamespace compiler option [Visual Basic]
ms.assetid: e9245edf-6bef-420d-a7c7-324117752783
caps.latest.revision: 13
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
ms.openlocfilehash: 7b261efeb829a6c0b035d7364c63074412a91c7f
ms.lasthandoff: 03/13/2017

---
# <a name="rootnamespace"></a>/rootnamespace
Especifica un espacio de nombres para todas las declaraciones de tipos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/rootnamespace:namespace  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`namespace`|El nombre del espacio de nombres en el que se desean englobar todas las declaraciones de tipo para el proyecto actual.|  
  
## <a name="remarks"></a>Comentarios  
 Si utiliza el archivo ejecutable de Visual Studio (Devenv.exe) para compilar un proyecto creado en el entorno de desarrollo integrado de Visual Studio, use `/rootnamespace` para especificar el valor de la <xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A>propiedad.</xref:VSLangProj80.VBProjectProperties3.RootNamespace%2A> Consulte [Devenv Command Line Switches](https://docs.microsoft.com/visualstudio/ide/reference/devenv-command-line-switches) para obtener más información.  
  
 Utilice el Desensamblador de MSIL de common language runtime (I`ldasm.exe`) para ver los nombres de espacio de nombres en el archivo de salida.  
  
|Para establecer /rootnamespace en Visual Studio de entorno de desarrollo integrado|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el **proyecto** menú, haga clic en **propiedades**. Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en la pestaña **Aplicación** .<br />3.  Modifique el valor en el **Root Namespace** cuadro.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `In.vb` y engloba todas las declaraciones de tipos en el espacio de nombres `mynamespace`.  
  
```  
vbc /rootnamespace:mynamespace in.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Ildasm.exe (Desensamblador IL)](https://msdn.microsoft.com/library/f7dy01k1)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
