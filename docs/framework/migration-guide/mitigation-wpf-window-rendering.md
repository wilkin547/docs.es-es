---
title: "Mitigación: representación de ventanas de WPF"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 28ed6bf8-141b-4b73-a4e3-44a99fae5084
caps.latest.revision: 3
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 57d4cc56cc8d3a4dc3614043779eb09d7a8b8e25
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---
# <a name="mitigation-wpf-window-rendering"></a>Mitigación: representación de ventanas de WPF
En [!INCLUDE[net_v46](../../../includes/net-v46-md.md)], ejecutado en Windows 8 y versiones posteriores, la ventana en su totalidad se representa sin recortes al extenderse más allá de una sola pantalla en un escenario de varios monitores.  
  
## <a name="impact"></a>Impacto  
 En general, la representación de una ventana completa en varios monitores sin recortes es el comportamiento esperado. Sin embargo, en Windows 7 y en versiones anteriores, las ventanas de WPF se recortan al extenderse más allá de una sola pantalla, ya que la representación de una parte de la ventana en el segundo monitor tiene un impacto considerable en el rendimiento.  
  
 El impacto preciso de la representación de ventanas de WPF en varios monitores con Windows 8 y versiones posteriores no se puede cuantificar de forma precisa, ya que depende de muchos factores. En algunos casos podría producir un impacto negativo en el rendimiento, sobre todo para los usuarios que ejecutan aplicaciones con muchos gráficos y que tienen ventanas que ocupan varios monitores. En otros casos, puede que lo único que quiera es tener un comportamiento constante en todas las versiones de .NET Framework.  
  
## <a name="mitigation"></a>Mitigación  
 Puede deshabilitar este cambio y volver al comportamiento anterior, en el que se recorta una ventana de WPF al extenderse más allá de una pantalla. Existen dos modos para hacer esto:  
  
-   Puede agregar el elemento `<EnableMultiMonitorDisplayClipping>` a la sección `<appSettings>` del archivo de configuración de la aplicación para habilitar o deshabilitar este comportamiento en las aplicaciones que se ejecutan en Windows 8 o versiones posteriores. Por ejemplo, la siguiente sección de configuración deshabilita la representación sin recortes:  
  
    ```xml  
    <appSettings>  
        <add key="EnableMultiMonitorDisplayClipping" value="true"/>  
      </appSettings>  
    ```  
  
     La opción de configuración `<EnableMultiMonitorDisplayClipping>` puede tener cualquiera de estos dos valores:  
  
    -   `true` para habilitar el recorte de ventanas para supervisar los límites durante la representación.  
  
    -   `false` para deshabilitar el recorte de ventanas para supervisar los límites durante la representación.  
  
-   Estableciendo la propiedad <xref:System.Windows.CoreCompatibilityPreferences.EnableMultiMonitorDisplayClipping%2A> en `true` al iniciar la aplicación.  
  
## <a name="see-also"></a>Vea también  
 [Cambios en el runtime](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-6.md)

