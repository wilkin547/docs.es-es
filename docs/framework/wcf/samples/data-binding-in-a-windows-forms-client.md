---
title: Enlace de datos en un cliente de Windows Forms
ms.date: 03/30/2017
ms.assetid: a2a30b37-d6e2-4552-820e-e60b2bbe8829
ms.openlocfilehash: 07af2f2e604c8eab7eca9908e0985fefee5b273f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96289456"
---
# <a name="data-binding-in-a-windows-forms-client"></a>Enlace de datos en un cliente de Windows Forms

Este ejemplo muestra cómo enlazar a los datos devueltos por un servicio de Windows Communication Foundation (WCF) en una aplicación Windows Forms.  
  
> [!NOTE]
> El procedimiento de configuración y las instrucciones de compilación de este ejemplo se encuentran al final de este tema.  
  
 Este ejemplo muestra un servicio que implementa un contrato que define un patrón de comunicación de solicitud y respuesta. El ejemplo consta de una aplicación de Windows Forms de cliente (. exe) y un servicio WCF hospedado por Internet Information Services (IIS).  
  
 El contrato se define mediante la interfaz `IWeatherService`, que expone una operación denominada `GetWeatherData`. Esta operación acepta una matriz de ciudades y devuelve una matriz de objetos `WeatherData` que representan la temperatura alta y baja prevista para una ciudad.  
  
 El enlace de datos se produce en el cliente de la aplicación de Windows Forms. Un `DataGridView`, se define en el Diseñador de Windows Forms, que es una representación gráfica de los datos.  También se crea un objeto `BindingSource` con nombre intermedio. El origen de datos de `BindingSource` se establece en la matriz de datos que devuelve el servicio. La finalidad de `BindingSource` es proporcionar una capa de direccionamiento indirecto entre los datos y la vista de datos. Toda interacción con los datos, como navegación, ordenación, filtrado y actualización, se lleva a cabo mediante llamadas al componente `BindingSource`. Para lograr el enlace de datos `DataGridView`, el `datasource` del `DataGridView` está establecido en el objeto `BindingSource`. Todos los datos devueltos por el servicio WCF se muestran gráficamente al usuario.  Cada vez que el usuario hace clic en el botón, se actualizan los datos devueltos automáticamente en el objeto `DataGridView` enlazado a datos.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>Configurar, compilar y ejecutar el ejemplo  
  
1. Asegúrese de que ha realizado el [procedimiento de instalación única para los ejemplos de Windows Communication Foundation](one-time-setup-procedure-for-the-wcf-samples.md).  
  
2. Para compilar el código C# o Visual Basic .NET Edition de la solución, siga las instrucciones de [Building the Windows Communication Foundation Samples](building-the-samples.md).  
  
3. Para ejecutar el ejemplo en una configuración de equipos única o cruzada, siga las instrucciones de [ejecución de los ejemplos de Windows Communication Foundation](running-the-samples.md).  
  
> [!IMPORTANT]
> Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Si este directorio no existe, vaya a [ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Scenario\DataBinding\WindowsForms`  
