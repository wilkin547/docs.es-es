---
title: "&quot;&lt;interfacename&gt;.&lt; MemberName&gt;&quot;ya está implementado por la clase base&quot;&lt;baseclassname&gt;&quot;. Reimplementación de &lt;tipo&gt; supone | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc42015
- bc42015
dev_langs:
- VB
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
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
ms.openlocfilehash: 5ab2041826f74fdc5aceab7b1ceb26563d9b3f0a
ms.lasthandoff: 03/13/2017

---
# <a name="39ltinterfacenamegtltmembernamegt39-is-already-implemented-by-the-base-class-39ltbaseclassnamegt39-re-implementation-of-lttypegt-assumed"></a>'&lt;interfacename&gt;.&lt; MemberName&gt;'ya está implementado por la clase base'&lt;baseclassname&gt;'. Reimplementación de &lt;tipo&gt; supone
Una propiedad, procedimiento o evento en una clase derivada utiliza una `Implements` cláusula que especifica un miembro de interfaz que ya está implementado en la clase base.  
  
 Una clase derivada puede volver a implementar un miembro de interfaz implementado por su clase base. Esto no es el mismo que reemplazar la implementación de la clase base. Para obtener más información, consulte [implementa](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC42015  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si piensa volver a implementar el miembro de interfaz, no es necesario realizar ninguna acción. Código de la clase derivada tiene acceso al miembro nuevamente implementado a menos que utilice el `MyBase` palabra clave para tener acceso a la implementación de la clase base.  
  
-   Si no tiene pensado volver a implementar el miembro de interfaz, quite la cláusula `Implements` de la declaración de propiedad, procedimiento o evento.  
  
## <a name="see-also"></a>Vea también  
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
