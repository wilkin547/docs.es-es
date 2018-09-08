---
title: SQLStoreExtensibility
ms.date: 03/30/2017
ms.assetid: 5da1b5a3-f144-41ba-b9c4-02818b28b15d
ms.openlocfilehash: f49d05244cf9f65a8e06f39c7e40391aaebd9f77
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2018
ms.locfileid: "44202380"
---
# <a name="sqlstoreextensibility"></a>SQLStoreExtensibility
En este ejemplo se muestran el uso y la configuración de propiedades promovidas en el almacén de instancias de flujo de trabajo de SQL. El almacén de instancias de flujo de trabajo de SQL es una implementación basada en SQL de un almacén de instancias. Permite a una instancia guardar y cargar su estado en y desde una base de datos SQL Server o SQL Server Express. La característica de extensibilidad del almacén permite al usuario definir propiedades que se guardan en el almacén de instancias. Estas propiedades se muestran en una vista de propiedades promovidas que permite al usuario consultarlas.  
  
 Este ejemplo consta de un flujo de trabajo que implementa un servicio de contador. Una vez invocado el método de inicio del servicio, este cuenta de 0 a 29. El contador se incrementa una vez cada 2 segundos. Después de cada recuento, el flujo de trabajo se guarda. El valor de contador actual se guarda en el almacén de instancias como una propiedad promovida.  
  
 Un host de servicio de flujo de trabajo autohospeda el flujo de trabajo de contador. El método `Main` del programa realiza las siguientes acciones:  
  
-   Crea una instancia del host del servicio de flujo de trabajo que hospeda el flujo de trabajo de contador y define los extremos bajo los que se puede alcanzar el flujo de trabajo de contador.  
  
-   Define un comportamiento del almacén de instancias de flujo de trabajo de SQL, que se utiliza para configurar el almacén de instancias de flujo de trabajo de SQL. Se indica al almacén que trate `CountStatus` como una propiedad promovida.  
  
-   Crea un cliente que llama al método de inicio del flujo de trabajo de contador.  
  
 Una vez iniciado el programa, el contador inicia la cuenta automáticamente. Tenga en cuenta que la carga y configuración del almacén de instancias de flujo de trabajo de SQL puede tardar unos segundos.  
  
 Para promover el valor del contador como una propiedad personalizada, se deben llevar a cabo los siguientes pasos:  
  
1.  La clase `CounterStatus` define una extensión de instancia de tipo <xref:System.Activities.Persistence.PersistenceParticipant>, que las actividades usan para proporcionar las variables de estado. `Count` se define como un valor de solo escritura. Cuando una instancia de flujo de trabajo llega a un punto de persistencia, la extensión de instancia guarda la propiedad `Count` en la colección de datos de persistencia.  
  
2.  Al crear el almacén de instancias, se define una nueva propiedad, `CountStatus`, a través del método `store.Promote()`.  
  
3.  La actividad `SaveCounter` del flujo de trabajo asigna el valor de contador actual al campo de estado `Count`.  
  
### <a name="to-use-this-sample"></a>Para utilizar este ejemplo  
  
1.  Cree la base de datos de almacén de instancias.  
  
    1.  Abra un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
    2.  Desplácese hasta el directorio de ejemplo (\WF\Basic\Persistence\SqlStoreExtensibility\CS) y ejecute CreateInstanceStore.cmd en el símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
        > [!WARNING]
        >  El script CreateInstanceStore.cmd intenta crear la base de datos en la instancia predeterminada de SQL Server 2008 Express. Si desea instalar la base de datos en una instancia diferente, modifique el script.  
  
2.  Abra [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], cargue la solución SqlStoreExtensibility.sln y compílela presionando CTRL+SHIFT+B.  
  
    > [!WARNING]
    >  Si instaló la base de datos en una instancia no predeterminada de SQL Server, actualice la cadena de conexión en el código antes de compilar la solución.  
  
3.  Ejecutar el ejemplo con privilegios de administrador, desplácese hasta el directorio de bin del proyecto (\WF\Basic\Persistence\SqlStoreExtensibility\bin\Debug) en [!INCLUDE[fileExplorer](../../../../includes/fileexplorer-md.md)], haciendo clic en SqlStoreExtensibility.exe y seleccione **ejecutar como Administrador**.  
  
### <a name="to-verify-the-sample-is-working-correctly"></a>Para comprobar que el ejemplo funciona correctamente  
  
1.  Usar SQL Server Management Studio para ver el contenido de la tabla de instancias seleccionando **bases de datos**, **InstanceStore**y, a continuación,  **System.ServiceModel.Activities.DurableInstancing.InstanceTable** en el Explorador de objetos, haga clic en **System.ServiceModel.Activities.DurableInstancing.InstanceTable** y seleccione  **Seleccionar las 1000 primeras filas**. Para obtener más información acerca de SQL Server Management Studio, consulte [Introducción a SQL Server Management Studio](https://go.microsoft.com/fwlink/?LinkId=165645)  
  
2.  Observe las instancias de flujo de trabajo enumeradas.  
  
3.  En un símbolo del sistema de [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)], ejecute el script QueryInstanceStore.cmd situado en el directorio de ejemplo (\WF\Basic\Persistence\SqlStoreExtensibility).  
  
4.  Observe el valor del contador que se muestra bajo **CountStatus**.  
  
5.  Ejecute el script varias veces para ver el **CountStats** cambio de valor.  
  
6.  Presione Entrar para finalizar la aplicación de flujo de trabajo.  
  
### <a name="to-uninstall-the-sample"></a>Para desinstalar el ejemplo  
  
1.  Quite la base de datos de almacén de instancias ejecutando el script RemoveInstanceStore.cmd situado en el directorio de ejemplo (\WF\Basic\Persistence\SqlStoreExtensibility).  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a [Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) Samples para .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) para descargar todos los Windows Communication Foundation (WCF) y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] ejemplos. Este ejemplo se encuentra en el siguiente directorio.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\SQLStoreExtensibility`  
  
## <a name="see-also"></a>Vea también  
 [Persistencia del flujo de trabajo](../../../../docs/framework/windows-workflow-foundation/workflow-persistence.md)  
 [Servicios de flujo de trabajo](../../../../docs/framework/wcf/feature-details/workflow-services.md)  
 [Ejemplos de persistencia y el hospedaje de AppFabric](https://go.microsoft.com/fwlink/?LinkId=193961)
