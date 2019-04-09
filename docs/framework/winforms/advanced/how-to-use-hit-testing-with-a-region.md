---
title: Filtrar para usar la comprobación de visitas en una región
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- hit tests [Windows Forms], using regions
- regions [Windows Forms], hit testing
ms.assetid: 3a4c07cb-a40a-4d14-ad35-008f531910a8
ms.openlocfilehash: 136f15f1364fb2aed791b4a61d0f11411b055967
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150506"
---
# <a name="how-to-use-hit-testing-with-a-region"></a>Filtrar para usar la comprobación de visitas en una región
Es el propósito de la prueba de posicionamiento determinar si el cursor está sobre un objeto determinado, como un icono o un botón.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente crea una región en forma más mediante la unión de dos regiones rectangulares. Supongamos que la variable `point` contiene la ubicación del clic más reciente. El código comprueba si `point` está en la región en forma de signo más. Si el punto está en la región (una visita), la región se rellena con un pincel rojo opaco. En caso contrario, la región se rellena con un pincel rojo semitransparente.  
  
 [!code-csharp[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/CS/Class1.cs#31)]
 [!code-vb[System.Drawing.MiscLegacyTopics#31](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.MiscLegacyTopics/VB/Class1.vb#31)]  
  
## <a name="compiling-the-code"></a>Compilar el código  
 El ejemplo anterior está diseñado para su uso con Windows Forms y requiere <xref:System.Windows.Forms.PaintEventArgs> `e`, que es un parámetro de <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Drawing.Region>
- [Regiones de GDI+](regions-in-gdi.md)
- [Filtrar para usar el recorte en una región](how-to-use-clipping-with-a-region.md)
