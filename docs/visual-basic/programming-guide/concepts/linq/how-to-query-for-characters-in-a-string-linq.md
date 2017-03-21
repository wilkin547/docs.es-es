---
title: "Cómo: buscar caracteres en una cadena (LINQ) (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 499ebbe0-746c-4235-9dba-ce722c12b50e
caps.latest.revision: 4
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: dabd63e52707f3078c6cdc41db8c4f0e7dfbf70e
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-for-characters-in-a-string-linq-visual-basic"></a>Cómo: buscar caracteres en una cadena (LINQ) (Visual Basic)
Dado que la <xref:System.String>clase implementa la interfaz genérica <xref:System.Collections.Generic.IEnumerable%601>interfaz, cualquier cadena se puede consultar como una secuencia de caracteres.</xref:System.Collections.Generic.IEnumerable%601> </xref:System.String> Sin embargo, esto no es un uso habitual de LINQ. Para operaciones de coincidencia de patrón complejo, utilice la <xref:System.Text.RegularExpressions.Regex>clase.</xref:System.Text.RegularExpressions.Regex>  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se consulta una cadena para determinar el número de dígitos numéricos que contiene. Tenga en cuenta que la consulta se "reutiliza" después de que se ejecuta la primera vez. Esto es posible porque la propia consulta no almacena ningún resultado real.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
## <a name="compiling-the-code"></a>Compilar el código  
 Crear un proyecto destinado a .NET Framework versión 3.5 o posterior con una referencia a System.Core.dll y una `Imports` instrucción del espacio de nombres System.Linq.  
  
## <a name="see-also"></a>Vea también  
 [LINQ y cadenas (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)   
 [Cómo: combinar consultas LINQ con expresiones regulares (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-linq-queries-with-regular-expressions.md)
