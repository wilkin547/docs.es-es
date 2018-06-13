---
title: Realizar el seguimiento del uso de un archivo de texto
ms.date: 03/30/2017
ms.assetid: 56a82682-73c2-4b91-a206-4d8bb12c561b
ms.openlocfilehash: aa59ab8304c68873c938f42fc585be883b234ecc
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2018
ms.locfileid: "33805803"
---
# <a name="tracking-using-a-text-file"></a>Realizar el seguimiento del uso de un archivo de texto
Este ejemplo muestra cómo ampliar el seguimiento en Windows Workflow Foundation (WF) mediante la creación de un participante de seguimiento personalizado. Los participantes de seguimiento son clases de .NET Framework que reciben registros de seguimiento del motor en tiempo de ejecución a medida que se emiten. Puede crear un participante de seguimiento para transportar los eventos de seguimiento al destino necesario para su escenario. Por ejemplo, como parte de [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] se proporciona el participante de seguimiento de ETW (Seguimiento de eventos para Windows). El participante de seguimiento de este ejemplo escribe los registros en formato XML en un archivo de texto.  
  
## <a name="sample-details"></a>Detalles del ejemplo  
 Para optimizar la utilidad y solidez del participante de seguimiento, deben completarse algunos pasos adicionales para conectar correctamente el participante de seguimiento al motor en tiempo de ejecución. En la siguiente tabla se describen las clases utilizadas en este ejemplo para crear un participante de seguimiento que obedece los procedimientos recomendados.  
  
|Clase|Descripción|  
|-----------|-----------------|  
|`TextFileTrackingExtensionElement`|Se utiliza una clase <xref:System.ServiceModel.Configuration.BehaviorExtensionElement> para definir la sección de configuración utilizada para configurar el participante de seguimiento de archivo de texto. Esto permite a los usuarios especificar el destino del archivo de registro utilizando archivos de configuración estándar de .NET Framework.|  
|`TextFileTrackingBehavior`|Comportamientos de WCF permiten a los usuarios insertar extensiones en tiempo de ejecución. Este comportamiento agrega el participante de seguimiento al servicio cuando este se inicia.|  
|`TextFileTrackingParticipant`|El participante de seguimiento que recibe los participantes de seguimiento en tiempo de ejecución y los almacena en un archivo de registro como XML.|  
  
## <a name="behavior-extension-elements-configuration"></a>Configuración de elementos de extensión de comportamiento  
 Para usar mediante archivos de configuración de .NET Framework el elemento de extensión de comportamiento previamente descrito, se necesita un paso más. En los archivos de configuración donde se va a usar la extensión se debe incluir la siguiente configuración.  
  
```xml  
<system.serviceModel>  
    <extensions>  
      <behaviorExtensions>  
        <add name="textFileTracking" type="Microsoft.Samples.TextFileTracking.TextFileTrackingExtensionElement, WFStockPriceApplication, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
      </behaviorExtensions>  
    </extensions>  
…  
  </system.serviceModel>  
```  
  
> [!NOTE]
>  Vea el archivo Web.config del ejemplo para el uso del ejemplo completo de la configuración de elementos de extensión de comportamiento.  
  
## <a name="custom-tracking-records"></a>Registros de seguimiento personalizados  
 El archivo GetStockPrices.cs muestra cómo crear registros de seguimiento personalizados desde una actividad <xref:System.Activities.CodeActivity>. Busque este registro al ejecutar el ejemplo.  
  
#### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Abra el archivo de solución de WFStockPriceApplication.sln con [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
2.  Para compilar la solución, presione Ctrl+MAYÚS+B.  
  
3.  Para ejecutar la solución, presione CTRL+F5.  
  
     La ventana del explorador se abre y muestra la lista de directorios de la aplicación.  
  
4.  En el explorador, haga clic en StockPriceService.xamlx.  
  
5.  El explorador muestra la **StockPriceService** página, que contiene la dirección wsdl de servicio local. Copie esta dirección.  
  
     Un ejemplo de la dirección wsdl de servicio local es http://localhost:53797/StockPriceService.xamlx?wsdl.  
  
6.  Mediante [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], vaya a la carpeta de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] (la carpeta de instalación predeterminada es %SystemDrive%\Program Files\Microsoft Visual Studio 10.0). A continuación, busque la subcarpeta Common7\IDE\.  
  
7.  Haga doble clic en el archivo WcfTestClient.exe para iniciar el Cliente de prueba WCF.  
  
8.  En el cliente de prueba WCF, seleccione **Agregar servicio...** desde el **archivo** menú.  
  
9. Pegue en el cuadro de texto la dirección URL que acaba de copiar.  
  
10. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.  
  
11. Pruebe el servicio con el Cliente de prueba WCF.  
  
    1.  En el cliente de prueba WCF, haga doble clic en **GetStockPrice()** en el **IStockPriceService** nodo.  
  
         El **GetStockPrice()** método aparece en el panel derecho, con un parámetro.  
  
    2.  Escriba Contoso como valor para el parámetro.  
  
    3.  Haga clic en **invocar**.  
  
12. Vea los eventos seguidos en el archivo de registro localizado en el directorio de datos de la aplicación en %APPDATA%\trackingRecords.log.  
  
    > [!NOTE]
    >  % APPDATA % es una variable de entorno que se resuelve en %SystemDrive%\Users\\< nombre de usuario\>\AppData\Roaming en [!INCLUDE[wv](../../../../includes/wv-md.md)], [!INCLUDE[lserver](../../../../includes/lserver-md.md)], o Windows Server 2008.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si este directorio no existe, vaya a [Windows Communication Foundation (WCF) y ejemplos de Windows Workflow Foundation (WF) para .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Tracking\TextFileTracking`  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de supervisión de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193959)
