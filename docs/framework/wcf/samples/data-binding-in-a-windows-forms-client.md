---
title: Enlace de datos en un cliente de Windows Forms
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2a30b37-d6e2-4552-820e-e60b2bbe8829
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b78cfbd63687fc7288c945ebcbec790150efed61
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="data-binding-in-a-windows-forms-client"></a>Enlace de datos en un cliente de Windows Forms
Este ejemplo muestra cómo enlazar los datos devueltos por un servicio [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] en una aplicación de Windows Forms.  
  
> [!NOTE]
>  El procedimiento de configuración y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Este ejemplo muestra un servicio que implementa un contrato que define un patrón de comunicación de solicitud y respuesta. Este ejemplo se compone de una aplicación Windows Forms de cliente (.exe) y un servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] alojado en Internet Information Services (IIS).  
  
 El contrato se define mediante la interfaz `IWeatherService`, que expone una operación denominada `GetWeatherData`. Esta operación acepta una matriz de ciudades y devuelve una matriz de objetos `WeatherData` que representan la temperatura alta y baja prevista para una ciudad.  
  
 El enlace de datos se produce en el cliente de la aplicación de Windows Forms. Un `DataGridView`, se define en el Diseñador de Windows Forms, que es una representación gráfica de los datos.  También se crea un objeto `BindingSource` con nombre intermedio. El origen de datos de `BindingSource` se establece en la matriz de datos que devuelve el servicio. La finalidad de `BindingSource` es proporcionar una capa de direccionamiento indirecto entre los datos y la vista de datos. Toda interacción con los datos, como navegación, ordenación, filtrado y actualización, se lleva a cabo mediante llamadas al componente `BindingSource`. Para lograr el enlace de datos `DataGridView`, el `datasource` del `DataGridView` está establecido en el objeto `BindingSource`. Después se muestran gráficamente todos los datos devueltos del servicio [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] al usuario.  Cada vez que el usuario hace clic en el botón, se actualizan los datos devueltos automáticamente en el objeto `DataGridView` enlazado a datos.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1.  Asegúrese de que ha llevado a cabo la [procedimiento de instalación de un solo uso para los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Para ejecutar el ejemplo en una configuración de equipo único o de varios, siga las instrucciones de [ejecutando los ejemplos de Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WindowsForms`  
  
## <a name="see-also"></a>Vea también
