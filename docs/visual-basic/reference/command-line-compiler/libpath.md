---
title: /LIBPATH | Documentos de Microsoft
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
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
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
ms.openlocfilehash: cc534e782cff34f0c4882f3da2af973fed69ff80
ms.lasthandoff: 03/13/2017

---
# <a name="libpath"></a>/libpath
Especifica la ubicación de ensamblados de referencia.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/libpath:dirList  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`dirList`|Obligatorio. Lista delimitada por punto y coma de directorios para que el compilador busque en caso de un ensamblado de referencia no se encuentra en uno el directorio de trabajo actual (el directorio desde el que se invoca el compilador) o el directorio del sistema de common language runtime. Si el nombre del directorio contiene un espacio, encierre el nombre entre comillas ("").|  
  
## <a name="remarks"></a>Comentarios  
 El `/libpath` opción especifica la ubicación de ensamblados al que hace referencia el [/reference](../../../visual-basic/reference/command-line-compiler/reference.md) opción.  
  
 El compilador busca referencias a ensamblados que no están completamente calificadas en el orden siguiente:  
  
1.  Directorio de trabajo actual. Éste es el directorio desde el que se invoca el compilador.  
  
2.  El directorio de sistema common language runtime.  
  
3.  Directorios especificados por `/libpath`.  
  
4.  Directorios especificados por la variable de entorno LIB.  
  
 El `/libpath` opción es aditiva; al especificar más de una vez, anexa nuevos valores a los que.  
  
 Use `/reference` para especificar una referencia de ensamblado.  
  
|Para establecer /libpath en Visual Studio de entorno de desarrollo integrado|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el **proyecto** menú, haga clic en **propiedades**. Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en el **referencias** ficha.<br />3.  Haga clic en el **hacer referencia a rutas de acceso... ** botón.<br />4.  En el **las rutas de acceso de referencia** cuadro de diálogo, escriba el nombre del directorio en el **carpeta:** cuadro.<br />5.  Haga clic en **Agregar carpeta**.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `T2.vb` para crear un archivo .exe. El compilador busca en el directorio de trabajo, en el directorio raíz de la unidad C: y en el directorio New Assemblies de la unidad C: de referencias de ensamblado.  
  
```  
vbc /libpath:c:\;"c:\New Assemblies" /reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Ensamblados y caché Global de ensamblados](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)   
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
