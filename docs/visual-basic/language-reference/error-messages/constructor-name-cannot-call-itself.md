---
title: "Constructor &#39; &lt;nombre&gt;&#39; no se puede llamar a sí mismo"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30298
- vbc30298
helpviewer_keywords:
- BC30298
ms.assetid: 2d77b7f4-0640-4f89-9c65-f101fd2847c0
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 2361d6f4d710e17a4f4e29ac03bfde523191fa83
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="constructor-39ltnamegt39-cannot-call-itself"></a>Constructor &#39; &lt;nombre&gt;&#39; no se puede llamar a sí mismo
A `Sub New` procedimiento en una clase o estructura se llama a sí mismo.  
  
 El propósito de un constructor es inicializar una instancia de una clase o estructura cuando es el primero creado. Una clase o estructura puede tener varios constructores, siempre que tengan listas de parámetros diferentes. Un constructor tiene permiso para llamar a otro constructor para realizar su funcionalidad además de su propio. Pero carece de significado para un constructor llame a sí mismo y, de hecho produciría una recursividad infinita si permite.  
  
 **Id. de error:** BC30298  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Compruebe la lista de parámetros del constructor que se va a llamar. Debe ser diferente de la del constructor que realiza la llamada.  
  
2.  Si no desea llamar a un constructor diferente, quite el `Sub New` llamar completamente.  
  
## <a name="see-also"></a>Vea también  
 [Duración de los objetos: cómo se crean y destruyen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
