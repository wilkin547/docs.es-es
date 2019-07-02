---
title: Información general de gráficos
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: f0e2fd9dcf31e5fdce16b5a3b6fd21eab6eab66a
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505323"
---
# <a name="overview-of-graphics"></a>Información general de gráficos
GDI + es una interfaz de programación de aplicaciones (API) que forma el subsistema del sistema operativo Microsoft Windows. GDI + es responsable de mostrar información en pantallas e impresoras. Como sugiere su nombre, GDI + es la sucesora de GDI, la interfaz de dispositivo gráfico incluida en versiones anteriores de Windows.  
  
## <a name="managed-class-interface"></a>Interfaz de clases administradas  
 La API de GDI + se expone a través de un conjunto de clases implementadas como código administrado. Este conjunto de clases se denomina el *interfaz de clases administradas* a GDI +. Los espacios de nombres siguientes constituyen la interfaz de clases administradas:  
  
- <xref:System.Drawing>  
  
- <xref:System.Drawing.Drawing2D>  
  
- <xref:System.Drawing.Imaging>  
  
- <xref:System.Drawing.Text>  
  
- <xref:System.Drawing.Printing>  
  
 Con una interfaz de dispositivo de gráficos, como GDI +, puede mostrar información en una pantalla o impresora sin tener que preocuparse sobre los detalles de un dispositivo de presentación determinado. El programador realiza las llamadas a métodos proporcionados por las clases de GDI +. A su vez, estos métodos realizan las llamadas adecuadas a controladores de dispositivos específicos. GDI + aísla la aplicación del hardware gráfico. Se trata del aislamiento que permite al programador crear aplicaciones independientes del dispositivo.  
  
## <a name="see-also"></a>Vea también

- [Graphics Overview](graphics-overview-windows-forms.md) (Información general sobre gráficos [Windows Forms])
