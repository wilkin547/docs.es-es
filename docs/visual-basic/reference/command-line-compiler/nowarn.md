---
title: /nowarn | Documentos de Microsoft
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
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: 15
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
ms.openlocfilehash: 61b145a9eb95f5357c7aa2983a96c31e8f2cef6a
ms.lasthandoff: 03/13/2017

---
# <a name="nowarn"></a>/nowarn
Suprime la capacidad del compilador para generar advertencias.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/nowarn[:numberList]  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`numberList`|Opcional. Lista delimitada por comas de los números de identificador de advertencia que el compilador debe suprimir. Si no se especifican identificadores de advertencia, se eliminarán todas las advertencias.|  
  
## <a name="remarks"></a>Comentarios  
 El `/nowarn` opción hace que el compilador no genere advertencias. Para suprimir una determinada advertencia, proporcione el identificador de advertencia para el `/nowarn` opción después de los dos puntos. Separe varios números de advertencia con comas.  
  
 Debe especificar la parte numérica del identificador de advertencia. Por ejemplo, si desea suprimir BC42024, la advertencia para las variables locales no utilizadas, especifique `/nowarn:42024`.  
  
 Para obtener más información sobre los números de Id. de advertencia, consulte [configurar advertencias en Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
|Para establecer /nowarn en Visual Studio de entorno de desarrollo integrado|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el **proyecto** menú, haga clic en **propiedades**. Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en el **compilar** ficha.<br />3.  Seleccione el **deshabilitar todas las advertencias** casilla de verificación para deshabilitar todas las advertencias.<br />     o bien<br />     Para deshabilitar una advertencia determinada, haga clic en **ninguno** desde la lista desplegable situada junto a la advertencia.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `T2.vb` y no muestra ninguna advertencia.  
  
```  
vbc /nowarn t2.vb  
```  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `T2.vb` y no muestra las advertencias para las variables locales no utilizadas (42024).  
  
```  
vbc /nowarn:42024 t2.vb  
```  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Configurar advertencias en Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic)
