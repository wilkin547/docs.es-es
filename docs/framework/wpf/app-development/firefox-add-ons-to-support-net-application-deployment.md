---
title: Complementos de Firefox para la implementación de aplicaciones .NET
ms.date: 03/30/2017
helpviewer_keywords:
- Firefox add-ons for .NET application deployment
- WPF plug-in for Firefox
- .NET application deployment [WPF], deploying with Firefox add-ons
- .NET Framework Assistant for Firefox
ms.assetid: 2403403b-9b14-48e9-b70d-fa288a3c9081
ms.openlocfilehash: 687f61bd3ec7d10c6aa66c20cd5eb58fcc56f18a
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636372"
---
# <a name="firefox-add-ons-to-support-net-application-deployment"></a>Complementos de Firefox para la implementación de aplicaciones .NET
El complemento de Windows Presentation Foundation (WPF) para Firefox y el Asistente para .NET Framework para Firefox permiten que las aplicaciones de explorador XAML (XBAP), los [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)]dinámicos y las aplicaciones ClickOnce funcionen con el explorador de Mozilla Firefox.  
  
## <a name="wpf-plug-in-for-firefox"></a>Complemento WPF para Firefox  
 El complemento WPF para Firefox permite que las XBAP y los archivos [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] sueltos se naveguen y se ejecuten en el nivel superior o en un IFRAME HTML en el explorador Firefox. Una aplicación XBAP es una aplicación de WPF que se puede publicar en un servidor web e iniciarse dentro de los exploradores admitidos. [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] dinámico es un archivo solo de XAML al que se puede navegar y que se muestra en los exploradores admitidos, de forma muy similar a un archivo XML.  
  
 El complemento de WPF para Firefox se instala con el .NET Framework 3,5. La ventana 7 incluye el .NET Framework 3,5, pero no incluye el complemento de WPF para Firefox. No se puede instalar el complemento WPF para Firefox en Windows 7.  
  
 El .NET Framework 4 no incluye el complemento de WPF para Firefox. Sin embargo, si se instalan las .NET Framework 3,5 y .NET Framework 4, el complemento de WPF para Firefox se instala con el .NET Framework 3,5. Por lo tanto .NET Framework 4 aplicaciones seguirán ejecutándose porque el host de WPF cargará la versión correcta del marco. Para obtener más información, vea [host de WPF (PresentationHost. exe)](wpf-host-presentationhost-exe.md).  
  
## <a name="net-framework-assistant-for-firefox"></a>Asistente de .NET Framework para Firefox  
 El Asistente para .NET Framework para Firefox permite que las aplicaciones ClickOnce independientes se ejecuten desde el explorador Firefox. El Asistente para .NET Framework para Firefox funciona de forma idéntica cuando se instala antes y después del explorador Firefox. Cuando se inicia el explorador Firefox y se instala el .NET Framework 3,5 SP1, Firefox busca e instala el Asistente para .NET Framework para Firefox. Los usuarios pueden configurar el Asistente para .NET Framework para que Firefox realice lo siguiente:  
  
- Preguntar antes de ejecutar la aplicación ClickOnce.  
  
- Informe de todas las versiones instaladas de la .NET Framework o solo de la versión más reciente.  
  
 El Asistente para .NET Framework para Firefox se incluye con el .NET Framework 3,5 SP1. Para obtener información acerca de cómo quitar el Asistente para .NET Framework para Firefox, consulte [eliminación del Asistente para .NET Framework para Firefox](https://go.microsoft.com/fwlink/?LinkId=177944).  
  
## <a name="see-also"></a>Vea también

- [Implementar una aplicación de WPF](deploying-a-wpf-application-wpf.md)
- [Información general sobre las aplicaciones de explorador XAML de WPF](wpf-xaml-browser-applications-overview.md)
- [Detectar si está instalado el complemento WPF para Firefox](how-to-detect-whether-the-wpf-plug-in-for-firefox-is-installed.md)
