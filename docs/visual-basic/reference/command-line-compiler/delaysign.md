---
title: /delaysign | Documentos de Microsoft
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
- delaysign compiler option [Visual Basic]
- /delaysign compiler option [Visual Basic]
- -delaysign compiler option [Visual Basic]
ms.assetid: c76e61a4-1884-4252-9fb2-377f99caa690
caps.latest.revision: 19
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
ms.openlocfilehash: 59d4ec227286c20b2b4ecf749a91f0c4ee8d25ca
ms.lasthandoff: 03/13/2017

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
 El `/delaysign` opción no tiene ningún efecto a menos que se utiliza con [/keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md) o [/keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md).  
  
 Cuando se solicita un ensamblado totalmente firmado, el compilador genera un valor hash del archivo que contiene el manifiesto (metadatos de ensamblado) y firma el hash con la clave privada. La firma digital resultante se almacena en el archivo que contiene el manifiesto. Cuando se retrasa la firma de un ensamblado, el compilador no calcula y almacena la firma, pero reserva espacio en el archivo para que la firma se pueda agregar más tarde.  
  
 Por ejemplo, si utiliza `/delaysign+`, un desarrollador de una organización distribuye versiones de prueba sin firma de un ensamblado que los evaluadores pueden utilizar y registrar con la caché global de ensamblados. Cuando finalice el trabajo en el ensamblado, la persona responsable de la clave privada de la organización puede firmar completamente el ensamblado. Esta división de funciones protege la clave privada de la organización de la divulgación, permitiendo que todos los desarrolladores trabajar en los ensamblados.  
  
 Consulte [crear y utilizar ensamblados](https://msdn.microsoft.com/library/xwb8f617) para obtener más información sobre cómo firmar un ensamblado.  
  
### <a name="to-set-delaysign-in-the-visual-studio-integrated-development-environment"></a>Para establecer /delaysign en Visual Studio de entorno de desarrollo integrado  
  
1.  Seleccione un proyecto en el **Explorador de soluciones**. En el **proyecto** menú, haga clic en **propiedades**. Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).  
  
2.  Haga clic en el **firma** ficha.  
  
3.  Establezca el valor de la **Retrasar firma sólo** cuadro.  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/ keyfile](../../../visual-basic/reference/command-line-compiler/keyfile.md)   
 [/ keycontainer](../../../visual-basic/reference/command-line-compiler/keycontainer.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
