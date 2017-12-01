---
title: "No accesible &#39; Main &#39; se encontró el método con una firma apropiada en &#39; &lt;nombre&gt;&#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30737
- vbc30737
helpviewer_keywords: BC30737
ms.assetid: 3f40bacd-3fac-4741-b204-852f693d4340
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 3f45dc17304c3c9d62b65760f2c1b5d461812a66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="no-accessible-39main39-method-with-an-appropriate-signature-was-found-in-39ltnamegt39"></a>No accesible &#39; Main &#39; se encontró el método con una firma apropiada en &#39; &lt;nombre&gt;&#39;
Las aplicaciones de línea de comandos deben tener un `Sub Main` definido. `Main`debe declararse como `Public Shared` si se ha definido en una clase o como `Public` si está definido en un módulo.  
  
 Para obtener más información sobre `Main`, consulte [NIB: Visual Basic Version of Hello, World](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c).  
  
 **Id. de error:** BC30737  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Definir una `Public Sub Main` procedimiento para el proyecto. Declara como `Shared` si y solo si se define dentro de una clase.  
  
## <a name="see-also"></a>Vea también  
 [NIB: versión de Visual Basic de Hola a todos](http://msdn.microsoft.com/en-us/9d030b60-e148-4366-a462-69532f02294c)  
 [Estructura de un programa de Visual Basic](../../../visual-basic/programming-guide/program-structure/structure-of-a-visual-basic-program.md)  
 [Procedimientos](../../../visual-basic/programming-guide/language-features/procedures/index.md)
