---
title: "Mitigación: virtualización y desplazamiento horizontal | Microsoft Docs"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-bcl
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d5bafd9b-a3b3-4f92-8241-2aad254fb1a9
caps.latest.revision: 6
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: Human Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 37c60fd8a3e3e4e44dc00e278f6edafcdd766c03
ms.contentlocale: es-es
ms.lasthandoff: 05/22/2017

---
# <a name="mitigation-horizontal-scrolling-and-virtualization"></a>Mitigación: virtualización y desplazamiento horizontal
Este cambio se aplica a un elemento <xref:System.Windows.Controls.ItemsControl> que realiza su propia virtualización en la dirección ortogonal hacia la dirección de desplazamiento principal. (El ejemplo principal es un control <xref:System.Windows.Controls.DataGrid> con <xref:System.Windows.Controls.DataGrid.EnableColumnVirtualization%2A> establecido en `true`).  Se cambió el resultado de determinadas operaciones de desplazamiento horizontales para producir resultados más intuitivos y más parecidos a los resultados de las operaciones verticales comparables.  Las operaciones específicas incluyen **Desplazar aquí** y **Borde derecho** para usar los nombres en el menú que se obtiene haciendo clic en con el botón derecho en una barra de desplazamiento horizontal.  Ambos calculan un desplazamiento de candidato y llaman a <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset%2A?displayProperty=fullName>.  Tras desplazarse hasta el desplazamiento nuevo, puede haber cambiado la definición de "aquí" o "borde derecho" porque el contenido recién desvirtualizado haya cambiado el valor de <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A?displayProperty=fullName>.  
  
## <a name="description-of-the-change"></a>Descripción del cambio  
 Antes de [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], la operación de desplazamiento simplemente utiliza el desplazamiento de candidato, aunque puede que ya no sea "aquí" o en "borde derecho".  Esto produce efectos como la miniatura de desplazamiento de "rebote", que se muestra mejor con un ejemplo.  Suponga que un control <xref:System.Windows.Controls.DataGrid> tiene <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A> establecido en 1000 y <xref:System.Windows.FrameworkElement.Width%2A>, en 200.  Un desplazamiento de "borde derecho" usa un desplazamiento del candidato de 1000 - 200 = 800.  Mientras se dirige al desplazamiento, las nuevas columnas se desvirtualizan; supongamos que son muy amplias, por lo que el elemento <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A> cambia a 2000.  El desplazamiento termina con <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A>=800, y el control de posición "rebota" de nuevo casi a la mitad de la barra de desplazamiento; precisamente a 800/2000 = 40 %.  
  
 A partir de [!INCLUDE[net_v462](../../../includes/net-v462-md.md)], se vuelve a calcular un nuevo desplazamiento de candidato cuando se produce esta situación. (Así es cómo funciona ya el desplazamiento vertical).  
  
## <a name="impact"></a>Impacto  
 El cambio produce una experiencia más predecible e intuitiva para el usuario final, pero también podría afectar a cualquier aplicación que dependa del valor exacto de <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName> después de un desplazamiento horizontal, independientemente de que la invocación la realice el usuario final o una llamada explícita a <xref:System.Windows.Controls.Primitives.IScrollInfo.SetHorizontalOffset%2A?displayProperty=fullName>.  
  
## <a name="mitigation"></a>Mitigación  
 Una aplicación que utiliza un valor de predicción para <xref:System.Windows.Controls.Primitives.IScrollInfo.HorizontalOffset%2A?displayProperty=fullName> debe cambiarse para recuperar el valor real y el valor de <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A> después de cualquier desplazamiento horizontal que podría cambiar <xref:System.Windows.Controls.Primitives.IScrollInfo.ExtentWidth%2A> debido a la virtualización.  
  
## <a name="see-also"></a>Vea también  
 [Cambios en el runtime](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6-2.md)
