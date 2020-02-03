---
title: Coordenadas
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
ms.openlocfilehash: c95888f31bfc867e9c028d53072ab3d710256708
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76734663"
---
# <a name="windows-forms-coordinates"></a>Coordenadas de formularios Windows Forms
El sistema de coordenadas de un Windows Forms se basa en las coordenadas del dispositivo y la unidad de medida básica al dibujar en Windows Forms es la unidad del dispositivo (normalmente, el píxel). Los puntos de la pantalla se describen mediante pares de coordenadas x e y, con las coordenadas x que aumentan a la derecha y las coordenadas y aumentan de arriba abajo. La ubicación del origen, con respecto a la pantalla, variará en función de si se especifican coordenadas de pantalla o de cliente.  
  
## <a name="screen-coordinates"></a>Coordenadas de pantalla  
 Una aplicación Windows Forms especifica la posición de una ventana en la pantalla en coordenadas de la pantalla. En el caso de las coordenadas de pantalla, el origen es la esquina superior izquierda de la pantalla. A menudo, la posición completa de una ventana se describe mediante una estructura <xref:System.Drawing.Rectangle> que contiene las coordenadas de pantalla de dos puntos que definen las esquinas superior izquierda e inferior derecha de la ventana.  
  
## <a name="client-coordinates"></a>Coordenadas de cliente  
 Una aplicación Windows Forms especifica la posición de los puntos en un formulario o control mediante coordenadas de cliente. El origen de las coordenadas de cliente es la esquina superior izquierda del área cliente del control o formulario. Las coordenadas de cliente garantizan que una aplicación puede utilizar valores de coordenadas coherentes mientras se dibuja en un formulario o control, independientemente de la posición del formulario o control en la pantalla.  
  
 Las dimensiones del área cliente también se describen mediante una estructura <xref:System.Drawing.Rectangle> que contiene las coordenadas de cliente para el área. En todos los casos, la coordenada superior izquierda del rectángulo se incluye en el área cliente, mientras que la coordenada inferior derecha se excluye. Las operaciones de gráficos no incluyen los bordes derecho e inferior de un área cliente. Por ejemplo, el método <xref:System.Drawing.Graphics.FillRectangle%2A> se llenará hasta el borde derecho e inferior del rectángulo especificado, pero no incluirá estos bordes.  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a>Asignación de un tipo de coordenada a otro  
 En ocasiones, puede que necesite asignar las coordenadas de pantalla a las coordenadas de cliente. Puede hacerlo fácilmente con los métodos <xref:System.Windows.Forms.Control.PointToClient%2A> y <xref:System.Windows.Forms.Control.PointToScreen%2A> disponibles en la clase <xref:System.Windows.Forms.Control>. Por ejemplo, la propiedad <xref:System.Windows.Forms.Control.MousePosition%2A> de <xref:System.Windows.Forms.Control> se registra en coordenadas de pantalla, pero puede que desee convertirlos en coordenadas de cliente.  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Windows.Forms.Control.PointToClient%2A>
- <xref:System.Windows.Forms.Control.PointToScreen%2A>
