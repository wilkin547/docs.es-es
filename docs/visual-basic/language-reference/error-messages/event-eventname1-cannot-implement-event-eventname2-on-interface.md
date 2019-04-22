---
title: El evento '<eventname1>' no puede implementar el evento '<eventname2>' en la interfaz '<interface>' porque sus tipos delegados '<delegate1>' y '<delegate2>' no coinciden
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: 9581168fa86f8f0715e004b60c2eb2a813cd38ab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "58840528"
---
# <a name="event-eventname1-cannot-implement-event-eventname2-on-interface-interface-because-their-delegate-types-delegate1-and-delegate2-do-not-match"></a>Evento '\<eventname1 >' no se puede implementar el evento '\<eventname2 >' en la interfaz '\<interfaz >' porque sus tipos de delegado\<delegate1 >' y '\<delegate2 >' no coinciden
Visual Basic no puede implementar un evento porque el tipo de delegado del evento no coincide con el tipo de delegado del evento en la interfaz. Este error puede producirse cuando define varios eventos en una interfaz e intenta implementarlos juntos con el mismo evento. Un evento puede implementar dos o más eventos solo si todos los eventos implementados se declaran con la sintaxis `As` y si se especifica el mismo tipo delegado.  
  
 **Identificador de error:** BC31423  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Implemente los eventos por separado.  
  
     -O bien-  
  
-   Definir los eventos en la interfaz usando el `As` sintaxis y especifique el mismo tipo de delegado.  
  
## <a name="see-also"></a>Vea también

- [Event (instrucción)](../../../visual-basic/language-reference/statements/event-statement.md)
- [Delegate (instrucción)](../../../visual-basic/language-reference/statements/delegate-statement.md)
- [Eventos](../../../visual-basic/programming-guide/language-features/events/index.md)
