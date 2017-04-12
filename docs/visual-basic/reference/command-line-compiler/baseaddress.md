---
title: /BaseAddress | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- /baseaddress
- baseaddress
dev_langs:
- VB
helpviewer_keywords:
- -baseaddress compiler option [Visual Basic]
- /baseaddress compiler option [Visual Basic]
- baseaddress compiler option [Visual Basic]
ms.assetid: c982bcf2-46e5-47a2-bc8f-a5cc32b7dc47
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
ms.openlocfilehash: 527a7c348583498f46ee094ef9b9eec9abf1bcd0
ms.lasthandoff: 03/13/2017

---
# <a name="baseaddress"></a>/baseaddress
Especifica una dirección base predeterminada al crear un archivo DLL.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
/baseaddress:address  
```  
  
## <a name="arguments"></a>Argumentos  
  
|Término|Definición|  
|---|---|  
|`address`|Obligatorio. La dirección base del archivo DLL. Esta dirección debe especificarse como un número hexadecimal.|  
  
## <a name="remarks"></a>Comentarios  
 La dirección base predeterminada para un archivo DLL se establece el [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort_md.md)].  
  
 Tenga en cuenta que la palabra de orden inferior de esta dirección se redondea. Por ejemplo, si especifica 0 x 11110001, se redondea como 0 x 11110000.  
  
 Para completar el proceso de firma para un archivo DLL, utilice la `–R` opción de la herramienta nombre seguro (Sn.exe).  
  
 Esta opción se omite si el destino no es un archivo DLL.  
  
|Para establecer /baseaddress en el IDE de Visual Studio|  
|---|  
|1.  Seleccione un proyecto en el **Explorador de soluciones**. En el **proyecto** menú, haga clic en **propiedades**. Para obtener más información, consulte [Introducción al Diseñador de proyectos](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).<br />2.  Haga clic en el **compilar** ficha.<br />3.  Haga clic en **Avanzado**.<br />4.  Modifique el valor en el **dirección base del archivo DLL:** cuadro. **Nota:** el **dirección base del archivo DLL:** cuadro es de solo lectura a menos que el destino es un archivo DLL.|  
  
## <a name="see-also"></a>Vea también  
 [Compilador de línea de comandos de Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)   
 [/target (Visual Basic)](../../../visual-basic/reference/command-line-compiler/target.md)   
 [Líneas de comandos de compilación de ejemplo](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)   
 [Sn.exe (herramienta de nombre seguro)](https://msdn.microsoft.com/library/k5b5tt23)
