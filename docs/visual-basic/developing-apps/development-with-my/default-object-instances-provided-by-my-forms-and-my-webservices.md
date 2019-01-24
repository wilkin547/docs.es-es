---
title: Instancias de objeto predeterminadas proporcionadas por My.Forms y My.WebServices (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 9285e88e3dc9fd8b3731416b1c40811188d6a33d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54563605"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a>Instancias de objeto predeterminadas proporcionadas por My.Forms y My.WebServices (Visual Basic)
El [My.Forms](../../../visual-basic/language-reference/objects/my-forms-object.md) y [My.WebServices](../../../visual-basic/language-reference/objects/my-webservices-object.md) objetos proporcionan acceso a formularios, orígenes de datos y servicios Web XML utilizados por la aplicación. Para ello, proporcionan colecciones de *las instancias predeterminadas* de cada uno de estos objetos.  
  
## <a name="default-instances"></a>Instancias predeterminadas  
 Una instancia predeterminada es una instancia de la clase que proporciona el tiempo de ejecución y no es necesario declarar y crear instancias mediante la `Dim` y `New` instrucciones. El ejemplo siguiente muestra cómo podría haber declarado y crea una instancia de una instancia de un <xref:System.Windows.Forms.Form> clase llamada `Form1`, y cómo ahora se puede obtener una instancia predeterminada de este <xref:System.Windows.Forms.Form> a través de la clase `My.Forms`.  
  
 [!code-vb[VbVbcnMy#5](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_1.vb)]  
  
 [!code-vb[VbVbcnMy#6](../../../visual-basic/developing-apps/development-with-my/codesnippet/VisualBasic/default-object-instances-provided-by-my-forms-and-my-webservices_2.vb)]  
  
 El `My.Forms` object devuelve una colección de instancias predeterminadas para cada `Form` clase que exista en el proyecto. De forma similar, `My.WebServices` proporciona una instancia predeterminada de la clase de proxy para cada servicio Web que ha creado una referencia a en la aplicación.  
  
## <a name="see-also"></a>Vea también
- [My.Forms (objeto)](../../../visual-basic/language-reference/objects/my-forms-object.md)
- [My.WebServices (objeto)](../../../visual-basic/language-reference/objects/my-webservices-object.md)
- [Cómo My depende del tipo de proyecto](../../../visual-basic/developing-apps/development-with-my/how-my-depends-on-project-type.md)
