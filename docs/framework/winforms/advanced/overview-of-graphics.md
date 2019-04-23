---
title: Información general de gráficos
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms], using managed interface
- graphics [Windows Forms], about graphics
ms.assetid: a602aef8-a8c8-4c36-9816-74e7bad96a68
ms.openlocfilehash: a95086645771de61cfc859e34b225992bc16eac9
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59103940"
---
# <a name="overview-of-graphics"></a>Información general de gráficos
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] es una interfaz de programación de aplicaciones (API) que forma el subsistema del sistema operativo Microsoft Windows. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] es responsable de mostrar información en pantallas e impresoras. Como sugiere su nombre, [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] es la sucesora de [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)], la interfaz de dispositivo gráfico incluida en versiones anteriores de Windows.  
  
## <a name="managed-class-interface"></a>Interfaz de clases administradas  
 El [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] API se expone a través de un conjunto de clases implementadas como código administrado. Este conjunto de clases se denomina el *interfaz de clases administradas* a [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. Los espacios de nombres siguientes constituyen la interfaz de clases administradas:  
  
-   <xref:System.Drawing>  
  
-   <xref:System.Drawing.Drawing2D>  
  
-   <xref:System.Drawing.Imaging>  
  
-   <xref:System.Drawing.Text>  
  
-   <xref:System.Drawing.Printing>  
  
 Con una interfaz de dispositivo de gráficos, como [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], puede mostrar información en una pantalla o impresora sin tener que preocuparse sobre los detalles de un dispositivo de presentación determinado. El programador llama a métodos proporcionados por clases [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)]. A su vez, estos métodos realizan las llamadas adecuadas a controladores de dispositivos específicos. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] aísla la aplicación del hardware gráfico. Se trata del aislamiento que permite al programador crear aplicaciones independientes del dispositivo.  
  
## <a name="see-also"></a>Vea también

- [Graphics Overview](graphics-overview-windows-forms.md) (Información general sobre gráficos [Windows Forms])
