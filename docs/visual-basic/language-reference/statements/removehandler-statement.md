---
title: "RemoveHandler (instrucción) | Documentos de Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
dev_langs:
- VB
helpviewer_keywords:
- RemoveHandler keyword
- RemoveHandler statement
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
caps.latest.revision: 14
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
ms.openlocfilehash: d35de576bd9e267800acc2a9bfd5761dd977622f
ms.lasthandoff: 03/13/2017

---
# <a name="removehandler-statement"></a>RemoveHandler (Instrucción)
Quita la asociación entre un evento y un controlador de eventos.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`event`|El nombre del evento que se está controlando.|  
|`eventhandler`|El nombre del procedimiento que controla actualmente el evento.|  
  
## <a name="remarks"></a>Comentarios  
 El `AddHandler` y `RemoveHandler` permiten iniciar y detener el control de eventos para un evento específico en cualquier momento durante la ejecución del programa.  
  
> [!NOTE]
>  Para los eventos personalizados, la `RemoveHandler` instrucción invoca el evento `RemoveHandler` descriptor de acceso. Para obtener más información sobre los eventos personalizados, vea [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Ejemplo  
 [!code-vb[VbVbalrEvents&#17;](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [AddHandler (instrucción)](../../../visual-basic/language-reference/statements/addhandler-statement.md)   
 [Identificadores](../../../visual-basic/language-reference/statements/handles-clause.md)   
 [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)   
 [Eventos](../../../visual-basic/programming-guide/language-features/events/index.md)
