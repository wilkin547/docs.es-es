---
title: Coordenadas de formularios Windows Forms
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms coordinates
- screen coordinates
- client coordinates
- coordinates [Windows Forms], Windows Forms
ms.assetid: cc06e61f-43b6-4408-a676-2542dcfcd96e
ms.openlocfilehash: 6feabadff17538f4a7368c348f7b72226e2d678e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2019
ms.locfileid: "59980660"
---
# <a name="windows-forms-coordinates"></a>Coordenadas de formularios Windows Forms
El sistema de coordenadas de un formulario Windows Forms se basa en coordenadas de dispositivo y la unidad básica de medida cuando se dibuja en Windows Forms es la unidad del dispositivo (normalmente, el píxel). Puntos en la pantalla se describen mediante pares de coordenadas x e y, con las coordenadas x si se aumenta a la derecha y las coordenadas y aumento de arriba a abajo. La ubicación de origen, con respecto a la pantalla, variará dependiendo de si está especificando las coordenadas de pantalla o el cliente.  
  
## <a name="screen-coordinates"></a>Coordenadas de pantalla  
 Una aplicación de Windows Forms especifica la posición de una ventana en la pantalla en coordenadas de pantalla. Para las coordenadas de pantalla, el origen es la esquina superior izquierda de la pantalla. A menudo se describe la posición de una ventana completa mediante un <xref:System.Drawing.Rectangle> estructura que contiene las coordenadas de pantalla de dos puntos que definen las esquinas superior izquierda e inferior derecha de la ventana.  
  
## <a name="client-coordinates"></a>Coordenadas de cliente  
 Una aplicación de Windows Forms especifica la posición de los puntos en un formulario o control mediante las coordenadas de cliente. El origen de coordenadas de cliente es la esquina superior izquierda del área cliente del control o formulario. Coordenadas de cliente aseguran de que una aplicación puede usar los valores de coordenadas coherentes al dibujar en un formulario o control, independientemente de la posición del formulario o control en la pantalla.  
  
 También se describen las dimensiones del área de cliente mediante un <xref:System.Drawing.Rectangle> estructura que contiene las coordenadas de cliente para el área. En todos los casos, la coordenada superior izquierda del rectángulo se incluye en el área de cliente, mientras se excluye la coordenada inferior derecha. Las operaciones de gráficos no incluyen los bordes derechos e inferior de un área de cliente. Por ejemplo el <xref:System.Drawing.Graphics.FillRectangle%2A> método se llenará con el borde derecho e inferior del rectángulo especificado, pero no incluirá estos bordes.  
  
## <a name="mapping-from-one-type-of-coordinate-to-another"></a>Asignación de un tipo de coordenadas a otro  
 En ocasiones, deberá asignar de coordenadas de pantalla a coordenadas de cliente. Puede hacerlo fácilmente mediante el uso de la <xref:System.Windows.Forms.Control.PointToClient%2A> y <xref:System.Windows.Forms.Control.PointToScreen%2A> métodos disponibles en la <xref:System.Windows.Forms.Control> clase. Por ejemplo, el <xref:System.Windows.Forms.Control.MousePosition%2A> propiedad de <xref:System.Windows.Forms.Control> se notifica en coordenadas de pantalla, pero es posible que desea convertir a coordenadas de cliente.  
  
## <a name="see-also"></a>Vea también

- <xref:System.Windows.Forms.Control.PointToClient%2A>
- <xref:System.Windows.Forms.Control.PointToScreen%2A>
