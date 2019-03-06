---
title: Filtrar Invalidar el árbol lógico
ms.date: 03/30/2017
helpviewer_keywords:
- overriding the logical tree [WPF]
- logical tree [WPF], overriding
ms.assetid: 0ae4d074-8113-4b06-b4fa-e0f39d4967a6
ms.openlocfilehash: bf3459fff1a90326794d6713dd39c73596b0e960
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375233"
---
# <a name="how-to-override-the-logical-tree"></a>Procedimiento Invalidar el árbol lógico
Aunque no es necesario en la mayoría de casos, los autores de controles avanzados tienen la opción de invalidar el árbol lógico.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se describe cómo crear subclases de <xref:System.Windows.Controls.StackPanel> para invalidar el árbol lógico, en este caso para aplicar un comportamiento que el panel solo puede tener y solo representará un único elemento secundario. No es necesariamente un comportamiento deseable desde un punto de vista práctico, pero se muestra a continuación para ilustrar el escenario de invalidación del árbol lógico normal de un elemento.  
  
 [!code-csharp[LogicalOverride#SingletonPanel](~/samples/snippets/csharp/VS_Snippets_Wpf/LogicalOverride/CSharp/SDKSampleLibrary/class1.cs#singletonpanel)]  
  
 Para más información acerca del árbol lógico, consulte [Árboles en WPF](trees-in-wpf.md).
