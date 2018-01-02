---
title: /nowarn
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- nowarn compiler option [Visual Basic]
- /nowarn compiler option [Visual Basic]
- -nowarn compiler option [Visual Basic]
ms.assetid: 7ebf2106-0652-4fdc-bf60-70fc86465d83
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d1eafe8d7ccd6f2c71b754dadc343518948e7146
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
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
|`numberList`|Opcional. Lista delimitada por comas de los números de Id. de advertencia que el compilador debería suprimir. Si no se especifican identificadores de advertencia, se suprimen todas las advertencias.|  
  
## <a name="remarks"></a>Comentarios  
 El `/nowarn` opción hace que el compilador no genere advertencias. Para suprimir una advertencia individual, proporcione el identificador de advertencia para el `/nowarn` opción después de los dos puntos. Separe varios números de advertencia con comas.  
  
 Debe especificar solo la parte numérica del identificador de advertencia. Por ejemplo, si desea suprimir BC42024, la advertencia para las variables locales no usadas, especifique `/nowarn:42024`.  
  
 Para obtener más información sobre los números de Id. de advertencia, consulte [configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
|Para establecer /nowarn en Visual Studio integra el entorno de desarrollo|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. <br />2.  Haga clic en la pestaña **Compilar**.<br />3.  Seleccione el **deshabilitar todas las advertencias** casilla de verificación para deshabilitar todas las advertencias.<br />     O bien<br />     Para deshabilitar una advertencia concreta, haga clic en **ninguno** desde la lista desplegable situada junto a la advertencia.|  
  
## <a name="example"></a>Ejemplo  
 El siguiente código compila `T2.vb` y no muestra las advertencias.  
  
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
 [Configurar advertencias en Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic)
