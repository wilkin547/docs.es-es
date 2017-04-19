---
title: "Expresión tiene el tipo &quot;&lt;typename&gt;&quot; que es un tipo restringido y no se puede utilizar para tener acceso a miembros heredados de &quot;Object&quot; o &quot;ValueType&quot; | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc31393
- vbc31393
dev_langs:
- VB
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
caps.latest.revision: 6
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
ms.openlocfilehash: aaedfd825889498159f92cbd1d615cc0064973d3
ms.lasthandoff: 03/13/2017

---
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a>Expresión tiene el tipo '&lt;typename&gt;' que es un tipo restringido y no se puede utilizar para tener acceso a miembros heredados de 'Object' o 'ValueType'
Una expresión se evalúa como un tipo que no se puede aplicar la conversión boxing common language runtime (CLR), pero tiene acceso a un miembro que requiere la conversión boxing.  
  
 *Conversión boxing* hace referencia al procesamiento necesario para convertir un tipo a `Object` o, en ocasiones, <xref:System.ValueType>.</xref:System.ValueType> Common language runtime no puede cuadro ciertos tipos de estructura, por ejemplo <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>y <xref:System.TypedReference>.</xref:System.TypedReference> </xref:System.RuntimeArgumentHandle> </xref:System.ArgIterator>  
  
 Esta expresión intenta utilizar el tipo restringido para llamar a un método heredado de <xref:System.Object>o <xref:System.ValueType>, como <xref:System.Object.GetHashCode%2A>o <xref:System.Object.ToString%2A>.</xref:System.Object.ToString%2A> </xref:System.Object.GetHashCode%2A> </xref:System.ValueType> </xref:System.Object> Para obtener acceso a este método [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] ha intentado una conversión boxing implícita que produce este error.  
  
 **Id. de error:** BC31393  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Localice la expresión que se evalúa en el tipo mencionado.  
  
2.  Busque la parte de la instrucción que intenta llamar al método heredado o <xref:System.Object> <xref:System.ValueType>.</xref:System.ValueType> </xref:System.Object>  
  
3.  Vuelva a escribir la instrucción para evitar la llamada al método.  
  
## <a name="see-also"></a>Vea también  
 [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
