---
title: El evento '<eventname1>' no puede implementar el evento '<eventname2>' en la interfaz '<interface>' porque sus tipos delegados '<delegate1>' y '<delegate2>' no coinciden
ms.date: 07/20/2015
f1_keywords:
- vbc31423
- bc31423
helpviewer_keywords:
- BC31423
ms.assetid: 2e754b66-5836-48ff-9697-b9c0d7085f18
ms.openlocfilehash: 32d6733580de8798a66c30d486b8439befd2af19
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409613"
---
# <a name="event-eventname1-cannot-implement-event-eventname2-on-interface-interface-because-their-delegate-types-delegate1-and-delegate2-do-not-match"></a>El evento '\<eventname1>' no puede implementar el evento '\<eventname2>' en la interfaz '\<interface>' porque sus tipos delegados '\<delegate1>' y '\<delegate2>' no coinciden
Visual Basic no puede implementar un evento porque el tipo delegado del evento no coincide con el tipo delegado del evento en la interfaz. Este error puede producirse cuando define varios eventos en una interfaz e intenta implementarlos juntos con el mismo evento. Un evento puede implementar dos o más eventos solo si todos los eventos implementados se declaran con la sintaxis `As` y si se especifica el mismo tipo delegado.  
  
 **Identificador de error:** BC31423  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Implemente los eventos por separado.  
  
     -O bien-  
  
- Defina los eventos en la interfaz mediante la `As` sintaxis y especifique el mismo tipo de delegado.  
  
## <a name="see-also"></a>Consulte también

- [Event (Instrucción)](../statements/event-statement.md)
- [Delegate (Instrucción)](../statements/delegate-statement.md)
- [Eventos](../../programming-guide/language-features/events/index.md)
