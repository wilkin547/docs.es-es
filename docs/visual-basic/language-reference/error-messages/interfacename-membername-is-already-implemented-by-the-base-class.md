---
title: '&#39;&lt;InterfaceName&gt;.&lt; MemberName&gt; &#39; ya está implementado por la clase base &#39; &lt;nombredeclasebase&gt;&#39;. Reimplementación de &lt;tipo&gt; supone'
ms.date: 07/20/2015
f1_keywords:
- vbc42015
- bc42015
helpviewer_keywords:
- BC42015
ms.assetid: 658c070a-113e-4bd8-b294-12c243191160
ms.openlocfilehash: 9054c293ede9db4637f23579407f2f76db29f2ba
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33588975"
---
# <a name="39ltinterfacenamegtltmembernamegt39-is-already-implemented-by-the-base-class-39ltbaseclassnamegt39-re-implementation-of-lttypegt-assumed"></a>&#39;&lt;InterfaceName&gt;.&lt; MemberName&gt; &#39; ya está implementado por la clase base &#39; &lt;nombredeclasebase&gt;&#39;. Reimplementación de &lt;tipo&gt; supone
Una propiedad, procedimiento o evento en una clase derivada utiliza un `Implements` cláusula que especifica un miembro de interfaz que ya se ha implementado en la clase base.  
  
 Una clase derivada puede volver a implementar un miembro de interfaz implementado por su clase base. Esto no es el mismo que reemplazar la implementación de la clase base. Para obtener más información, consulte [implementa](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
 De forma predeterminada, este mensaje es una advertencia. Para obtener información sobre cómo ocultar las advertencias o cómo tratarlas como errores, vea [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **Id. de error:** BC42015  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Si piensa volver a implementar el miembro de interfaz, no es necesario realizar ninguna acción. Código de la clase derivada tiene acceso al miembro nuevamente implementado a menos que utilice el `MyBase` palabra clave para tener acceso a la implementación de la clase base.  
  
-   Si no tiene pensado volver a implementar el miembro de interfaz, quite la cláusula `Implements` de la declaración de propiedad, procedimiento o evento.  
  
## <a name="see-also"></a>Vea también  
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)
