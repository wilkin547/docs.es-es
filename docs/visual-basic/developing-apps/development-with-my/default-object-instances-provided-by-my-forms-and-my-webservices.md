---
title: Instancias de objeto predeterminadas proporcionadas por My.Forms y My.WebServices (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 421995684201ec48d5e8aff9b0ed7640efd1e4b9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33582667"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a>Instancias de objeto predeterminadas proporcionadas por My.Forms y My.WebServices (Visual Basic)
El [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) y [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) objetos proporcionan acceso a formularios, orígenes de datos y servicios Web XML utilizados por la aplicación. Para ello, proporcionan colecciones de *instancias predeterminadas* de cada uno de estos objetos.  
  
## <a name="default-instances"></a>Instancias predeterminadas  
 Una instancia predeterminada es una instancia de la clase que se proporciona en tiempo de ejecución y no necesita ser declara y crea una instancia mediante el `Dim` y `New` las instrucciones. En el ejemplo siguiente se muestra cómo podría haber declara y crea una instancia de una instancia de un <xref:System.Windows.Forms.Form> clase llamada `Form1`, y cómo ahora se puede obtener una instancia predeterminada de este <xref:System.Windows.Forms.Form> a través de la clase `My.Forms`.  
  
 [!code-vb[VbVbcnMy#5](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_1.vb)]  
  
 [!code-vb[VbVbcnMy#6](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_2.vb)]  
  
 El `My.Forms` object devuelve una colección de instancias predeterminadas para cada `Form` clase que exista en el proyecto. De forma similar, `My.WebServices` proporciona una instancia predeterminada de la clase de proxy para cada servicio Web que ha creado una referencia a en la aplicación.  
  
## <a name="see-also"></a>Vea también  
 [My.Forms (objeto)](../../../visual-basic/language-reference/objects/my-forms-object.md)  
 [My.WebServices (objeto)](../../../visual-basic/language-reference/objects/my-webservices-object.md)  
 [Cómo My depende del tipo de proyecto](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
