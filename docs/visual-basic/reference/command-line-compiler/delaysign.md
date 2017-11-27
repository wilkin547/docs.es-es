---
title: /delaysign
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- delaysign compiler option [Visual Basic]
- /delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6c42e351808281d90eafdb6e61a3f1736ef15c9d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="delaysign"></a>/delaysign
Especifica si el ensamblado estará firmado total o parcialmente.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/delaysign[+ | -]  
```  
  
## <a name="arguments"></a>Argumentos  
 `+` &#124; `-`  
 Opcional. Use `/delaysign-` para firmar completamente un ensamblado. Use `/delaysign+` si desea colocar la clave pública en el ensamblado y reservar espacio para el hash firmado. De manera predeterminada, es `/delaysign-`.  
  
## <a name="remarks"></a>Comentarios  
 El `/delaysign` opción no tiene ningún efecto a menos que use con [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) o [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).  
  
 Cuando se solicita un ensamblado totalmente firmado, el compilador genera un valor hash para el archivo que contiene el manifiesto (metadatos del ensamblado) y firma dicho valor mediante la clave privada. La firma digital resultante se almacena en el archivo que contiene el manifiesto. Una vez un ensamblado con firma retrasada, el compilador no de proceso y se almacena la firma, pero reserva espacio en el archivo para que la firma se pueda agregar más tarde.  
  
 Por ejemplo, al usar `/delaysign+`, un desarrollador de una organización distribuye versiones de prueba sin firma de un ensamblado que los evaluadores pueden utilizar y registrar con la caché global de ensamblados. Cuando se completa el trabajo en el ensamblado, la persona responsable de la clave privada de la organización puede firmar completamente el ensamblado. Esta división de funciones protege la clave privada de la organización contra la divulgación, permitiendo a los desarrolladores trabajar en los ensamblados.  
  
 Vea [crear y utilizar ensamblados](https://msdn.microsoft.com/library/xwb8f617) para obtener más información sobre cómo firmar un ensamblado.  
  
### <a name="to-set-delaysign-in-the-visual-studio-integrated-development-environment"></a>Para establecer /delaysign en Visual Studio integra el entorno de desarrollo  
  
1.  Seleccione un proyecto en el **Explorador de soluciones**. En el menú **Proyecto**, haga clic en **Propiedades**. Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Haga clic en la pestaña **Firma**.  
  
3.  Establezca el valor el **Retrasar firma sólo** cuadro.  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)  
 [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)  
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
