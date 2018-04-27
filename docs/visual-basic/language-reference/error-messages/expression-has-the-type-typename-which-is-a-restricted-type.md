---
title: Expresión tiene el tipo &#39; &lt;typename&gt; &#39; que es un tipo restringido y no se puede usar para tener acceso a miembros heredados de &#39;objeto&#39; o &#39;ValueType&#39;
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc31393
- vbc31393
helpviewer_keywords:
- BC31393
ms.assetid: 2963cf3f-c527-4aa7-b67c-ee80b6d23186
caps.latest.revision: 6
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ab4e48c93a6a3c645bf9b5cc6c536d418022ae86
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2018
---
# <a name="expression-has-the-type-39lttypenamegt39-which-is-a-restricted-type-and-cannot-be-used-to-access-members-inherited-from-39object39-or-39valuetype39"></a>Expresión tiene el tipo &#39; &lt;typename&gt; &#39; que es un tipo restringido y no se puede usar para tener acceso a miembros heredados de &#39;objeto&#39; o &#39;ValueType&#39;
Una expresión se evalúa como un tipo que no se puede realizar la conversión boxing por common language runtime (CLR), pero tiene acceso a un miembro que requiere la conversión boxing.  
  
 La*conversión boxing* hace referencia al procesamiento necesario para convertir un tipo a `Object` o, en ocasiones, a <xref:System.ValueType>. Common language runtime no puede boxing a ciertos tipos de estructura, por ejemplo <xref:System.ArgIterator>, <xref:System.RuntimeArgumentHandle>, y <xref:System.TypedReference>.  
  
 Esta expresión intenta utilizar el tipo restringido para llamar a un método heredado de <xref:System.Object> o <xref:System.ValueType>, como <xref:System.Object.GetHashCode%2A> o <xref:System.Object.ToString%2A>. Para obtener acceso a este método, Visual Basic ha intentado una conversión boxing implícita que produce este error.  
  
 **Id. de error:** BC31393  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Localice la expresión que se evalúa en el tipo mencionado.  
  
2.  Busque la parte de la instrucción que intenta llamar al método se hereda de <xref:System.Object> o <xref:System.ValueType>.  
  
3.  Vuelva a escribir la instrucción para evitar la llamada al método.  
  
## <a name="see-also"></a>Vea también  
 [Conversiones implícitas y explícitas](../../../visual-basic/programming-guide/language-features/data-types/implicit-and-explicit-conversions.md)
