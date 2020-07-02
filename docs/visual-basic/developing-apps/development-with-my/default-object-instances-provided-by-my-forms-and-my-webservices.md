---
title: Instancias de objeto predeterminadas proporcionadas por My.Forms y My.WebServices
ms.date: 07/20/2015
helpviewer_keywords:
- My.WebServices object [Visual Basic], developing applications
- My.Forms object [Visual Basic], developing applications
- rapid application development (RAD), My.Forms
- rapid application development (RAD), My.WebServices
ms.assetid: de930027-9108-4f0c-b97c-5e7db4d6ef79
ms.openlocfilehash: 141f2f5f98499498d3c6732f7ae8d0abe6259ed9
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990249"
---
# <a name="default-object-instances-provided-by-myforms-and-mywebservices-visual-basic"></a>Instancias de objeto predeterminadas proporcionadas por My.Forms y My.WebServices (Visual Basic)

Los objetos [My.Forms](../../language-reference/objects/my-forms-object.md) y [My.WebServices](../../language-reference/objects/my-webservices-object.md) proporcionan acceso a formularios, orígenes de datos y servicios web XML utilizados por la aplicación. Proporcionan acceso a través de colecciones de *instancias predeterminadas* de cada uno de estos objetos.  
  
## <a name="default-instances"></a>Instancias predeterminadas  

 Una instancia predeterminada es una instancia de la clase proporcionada por el runtime y que no es necesario declarar y ni crear una instancia mediante las instrucciones `Dim` y `New`. En el ejemplo siguiente se muestra cómo se podría haber declarado y creado una instancia de una clase <xref:System.Windows.Forms.Form> denominada `Form1` y cómo ahora se puede obtener una instancia predeterminada de esta clase <xref:System.Windows.Forms.Form> a través de `My.Forms`.  
  
 [!code-vb[VbVbcnMy#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#5)]  
  
 [!code-vb[VbVbcnMy#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnMy/VB/Class1.vb#6)]  
  
 El objeto `My.Forms` devuelve una colección de instancias predeterminadas para todas las clases `Form` que existen en el proyecto. Del mismo modo, `My.WebServices` proporciona una instancia predeterminada de la clase de proxy para cada servicio web para el que se haya creado una referencia en la aplicación.  
  
## <a name="see-also"></a>Vea también

- [My.Forms (objeto)](../../language-reference/objects/my-forms-object.md)
- [My.WebServices (objeto)](../../language-reference/objects/my-webservices-object.md)
- [Cómo My depende del tipo de proyecto](how-my-depends-on-project-type.md)
