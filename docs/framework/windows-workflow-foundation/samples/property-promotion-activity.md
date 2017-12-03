---
title: "Actividad de promoción de propiedad"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 802196b7-1159-4c05-b41b-d3bfdfcc88d9
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 3e1237c0732b5422034db7c83c665c57c48486d7
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2017
---
# <a name="property-promotion-activity"></a>Actividad de promoción de propiedad
Este ejemplo proporciona una solución integral que incluye la característica Promoción de <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> directamente en el flujo de trabajo que crea la experiencia. Se proporciona una colección de elementos de configuración, actividades de flujo de trabajo y extensiones de flujo de trabajo que simplifican el uso de la característica Promoción. Además, el ejemplo contiene un flujo de trabajo sencillo que muestra cómo utilizar esta colección.  
  
> [!NOTE]
>  Los ejemplos se proporcionan exclusivamente con fines formativos. No están pensados para un entorno de producción y no se han probado en un entorno de producción. Microsoft no proporciona soporte técnico para estos ejemplos.  
  
## <a name="prerequisites"></a>Requisitos previos  
  
-   Una base de datos <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> inicializada  
  
-   [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)]  
  
## <a name="sample-projects"></a>Proyectos de ejemplo  
  
-   El **PropertyPromotionActivity** proyecto contiene archivos que pertenecen a los elementos de configuración específicos de la promoción, las actividades de flujo de trabajo y extensiones de flujo de trabajo.  
  
-   El **CounterServiceApplication** proyecto contiene un flujo de trabajo de ejemplo que usa el **SqlWorkflowInstanceStorePromotion** proyecto.  
  
-   Un script SQL (PropertyPromotionActivitySQLSample.sql) que se debe ejecutar contra la base de datos <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>.  
  
-   Un archivo de solución que vincula los dos proyectos [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)] (`PropertyPromotionActivity.sln`)  
  
## <a name="to-set-up-and-run-the-sample"></a>Configurar y ejecutar el ejemplo  
  
1.  Inicialice una base de datos de persistencia de flujo de trabajo.  
  
    1.  Navegue hasta el directorio de ejemplo (\WF\Basic\Persistence\PropertyPromotionActivity) y ejecute CreateInstanceStore.cmd.  
  
    2.  Si no dispone de privilegios de administrador, cree un inicio de sesión de SQL Server. En SQL Server Management Studio, vaya a **seguridad**, **inicios de sesión**. Haga clic en **inicios de sesión** y crear un nuevo inicio de sesión. Agregue el usuario ACL al rol SQL abriendo **bases de datos**, **InstanceStore**, **seguridad**. Haga clic en **usuarios** y seleccione **nuevo usuario**. Establecer el **nombre de inicio de sesión** para el usuario creado anteriormente. Agregue el usuario a la pertenencia al rol de la base de datos System.Activities.DurableInstancing.InstanceStoreUsers (y otros). Observe que el usuario ya podría existir (por ejemplo, el usuario dbo).  
  
2.  Abra el archivo de solución PropertyPromotionActivity.sln en [!INCLUDE[vs2010](../../../../includes/vs2010-md.md)].  
  
3.  Si creó el almacén de instancia en una base de datos distinta de una instalación local de SQL Server Express, a continuación debe actualizar la cadena de conexión a la base de datos. Modifique el archivo App.config en el **CounterServiceApplication** estableciendo el valor de la `connectionString` del atributo en el `sqlWorkflowInstanceStorePromotion` nodo para que apunte a la base de datos de persistencia que se inicializó en el paso 1.  
  
4.  Compile y ejecute la solución. Esto iniciará el servicio Counter WF e iniciará automáticamente una instancia de flujo de trabajo.  
  
5.  Seleccione rápidamente todas las filas de la vista [dbo]. [CounterService] en su base de datos de persistencia (esta vista se agregó al ejecutar CreateInstanceStore.cmd en el paso 1). Verá un conjunto de resultados similar al siguiente:  
  
    |InstanceId|CounterValue|CounterValueLastUpdated|  
    |----------------|------------------|-----------------------------|  
    |2FA2C302-929E-4C0D-8C25-768A3DA20CE5|12|2010-02-18 22:48:01.740|  
  
     Mientras sigue actualizando la vista, observará que CounterValue y CounterValueLastUpdated cambian cada dos segundos. Este es el intervalo en el que el contador se actualiza. CounterValue and CounterValueLastUpdated representan las propiedades que se han promovido para este flujo de trabajo.  
  
## <a name="to-remove-the-sample"></a>Para quitar el ejemplo  
  
-   Ejecute RemoveInstanceStore.cmd en el directorio de ejemplos (\WF\Basic\Persistence\PropertyPromotionActivity).  
  
## <a name="understanding-this-sample"></a>Descripción de este ejemplo  
 El ejemplo contiene dos proyectos y un archivo SQL:  
  
-   **CounterServiceApplication** es una aplicación de consola que hospeda un servicio Counter WF simple. Al recibir un mensaje unidireccional a través del extremo `Start`, el flujo de trabajo cuenta de 0 a 29, incrementando una variable de contador cada dos segundos. Después de cada incremento del contador, el flujo de trabajo persiste y las propiedades promovidas están actualizadas en la vista [dbo].[CounterService]. Cuando se ejecuta la aplicación de consola, hospeda el servicio WF y envía un mensaje al extremo `Start`, creando una instancia de Counter WF.  
  
-   **PropertyPromotionActivity** es una biblioteca de clases que contiene los elementos de configuración, actividades de flujo de trabajo y extensiones de flujo de trabajo que el **CounterServiceApplication** usa.  
  
-   **PropertyPromotionActivitySQLSample.sql** crea y agrega la vista [dbo]. [ CounterService] a la base de datos.  
  
### <a name="counterserviceapplication"></a>CounterServiceApplication  
  
#### <a name="using-the-sqlworkflowinstancestorepromotion-configuration-element"></a>Utilizar el elemento de configuración SqlWorkflowInstanceStorePromotion  
 El elemento de configuración `SqlWorkflowInstanceStorePromotion` se hereda del elemento de configuración `SqlWorkflowInstanceStore`, pero agrega un elemento de configuración adicional llamado `promotionSets`. El elemento `promotionSets` le permite al usuario especificar las propiedades promovidas mediante la configuración. Es el archivo de configuración que utiliza el ejemplo:  
  
```xml  
<sqlWorkflowInstanceStorePromotion connectionString ="Data Source=.;Initial Catalog=SqlWorkflowInstanceStoreTest;Integrated Security=True;">  
  <promotionSets>  
    <promotionSet name="CounterService">  
      <promotedValue propertyName="Count"/>  
      <promotedValue propertyName="LastIncrementedAt"/>  
    </promotionSet>  
  </promotionSets>  
</sqlWorkflowInstanceStorePromotion>  
```  
  
 Examine la definición para la vista [dbo].[CounterService].  
  
```sql  
create view [dbo].[CounterService] as  
      select [InstanceId],  
 [Value1] as [CounterValue],  
 [Value2] as [CounterValueLastUpdated]  
      from [System.Activities.DurableInstancing].[InstancePromotedProperties]  
      where [PromotionName] = 'CounterService'  
go  
```  
  
 Cuando una instancia de flujo de trabajo persiste, se inserta una fila en la vista `InstancePromotedProperties` vista para cada `PromotionSet` que se define en la configuración. Esta fila contiene todas las propiedades promovidasl de (una propiedad promocionada por columna) `PromotionSet` (una propiedad promovida por columna). La tupla recibe la clave de `PromotionSet`: `InstanceId, PromotionName`. En este ejemplo, tenemos un `PromotionSet` definido en configuración cuyo atributo de nombre es `CounterService`. Observe que el valor de columna `PromotionName` es igual al atributo de nombre del elemento `PromotionSet`.  
  
 El orden de los elementos `promotedValue` se correlaciona con la colocación de las propiedades promovidas en la vista `InstancePromotedProperties`. `Count` es el primer elemento `promotedValue`. Como resultado, se asigna a la columna `Value1` de la vista `InstancePromotedProperties`. `LastIncrementedAt` es el segundo elemento `promotedValue`. Como resultado, se asigna a la columna `Value2` de la vista `InstancePromotedProperties`.  
  
#### <a name="using-the-promotevalue-activity"></a>Utilizar la actividad PromoteValue  
 Examine el archivo CounterService.xamlx en el Diseñador [!INCLUDE[wf2](../../../../includes/wf2-md.md)]. Observe que hay dos actividades especiales en la definición de WF: `PromoteValue<DateTime>` y `PromoteValue<Int32>`.  
  
 La actividad `PromoteValue<Int32>` tiene su miembro `Name` definido como `Count`. Esto coincide con el primer elemento de `promotedValue` en la configuración y tiene `Value` definido como la variable de flujo de trabajo `Counter`. Cuando el flujo de trabajo persiste, la variable de flujo de trabajo `Counter` se guarda como una propiedad promovida en la columna `Value1` de la vista `InstancePromotedProperties`.  
  
 La actividad `PromoteValue<DateTime>` tiene su miembro `Name` definido como `LastIncrementedAt`. Esto coincide con el segundo elemento de `promotedValue` en la configuración y tiene `Value` definido como la variable de flujo de trabajo `TimeLastIncremented`. Esto significa que cuando el flujo de trabajo persiste, el valor para la variable de flujo de trabajo `TimeLastIncremented` se guardará como una propiedad promovida en la columna `Value2` de la vista `InstancePromotedProperties`.  
  
 Observe que la actividad `PromotedValue` también tiene un miembro Boolean llamado `ClearExistingPromotedData`. Cuando este miembro está establecido en `true`, se borran todos los valores de la propiedad promovida hasta ese punto del flujo de trabajo. Por ejemplo, si una actividad Sequence se define como sigue:  
  
1.  PromoteValue {nombre = "Count", valor = 3}  
  
2.  PromoteValue {nombre = "LastIncrementedAt", valor = 1-1-2000}  
  
3.  Conservar  
  
4.  PromoteValue {nombre = "Count", valor = 4, ClearExistingPromotedData = true}  
  
5.  Conservar  
  
 En la segunda persistencia, el valor promovido para `Count` será 4. Sin embargo, el valor promovido para `LastIncrementedAt` será `NULL`. Si `ClearExistingPromotedData` no se hubiera establecido en `true` para el paso 4, después de la segunda persistencia el valor promovido para Count sería 4. Como resultado, el valor promovido para `LastIncrementedAt` todavía sería 1-1-2000.  
  
### <a name="propertypromotionactivity"></a>PropertyPromotionActivity  
 Esta biblioteca de clases contiene las siguientes clases pública para simplificar uso de la característica Promoción de <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>.  
  
#### <a name="promotevalue-class"></a>Clase PromoteValue  
 Esta clase promueve una propiedad. El nombre de la propiedad promovida debería coincidir con un atributo de nombre de un elemento `promotedValue` de la configuración. Esta actividad se puede usar en el Diseñador de flujo de trabajo. Vea CounterServiceApplication para un uso del ejemplo.  
  
```csharp  
public class PromoteValue<T> : CodeActivity  
{  
    public PromoteValue()  
    {  
    }  
  
    public bool ClearExistingPromotedData { get; set; }  
    public string Name { get; set; }  
    public InArgument<T> Value { get; set; }  
}  
```  
  
 ClearExistingPromotedData (Bool)  
 Borra todos los valores que se promovieron antes de esta actividad.  
  
 Name (string)  
 El nombre que representa a esta propiedad. Esto debe coincidir con el atributo de nombre de un \<promotedValue > elemento en la configuración.  
  
 Valor (InArgument\<T >)  
 La variable / valor que desea almacenar en la columna.  
  
#### <a name="promotevalues-class"></a>Clase PromoteValues  
 Promueve varias propiedades. Los nombres de las propiedades promovidas deberían coincidir con todos los atributos de nombre de los elementos `promotedValue` de la configuración. El uso es similar al de la actividad `PromoteValue`, salvo por el hecho de que se pueden promover varias propiedades al mismo tiempo. Esta actividad no se puede usar en el Diseñador de flujo de trabajo.  
  
```  
public class PromoteValues : CodeActivity  
{  
    public PromoteValues()  
    {  
        this.ValuesToPromote = new Dictionary<string, InArgument>();  
    }  
  
    public bool ClearExistingPromotedData { get; set; }  
    public IDictionary<string, InArgument> ValuesToPromote { get; set; }  
}  
```  
  
#### <a name="sqlworkflowinstancestorepromotionbehavior"></a>SqlWorkflowInstanceStorePromotionBehavior  
 Deriva de `SqlWorkflowInstanceStoreBehavior`. Esta clase derivada agrega un participante de persistencia personalizado (también una parte de esta biblioteca) como una extensión de flujo de trabajo. La implementación de las dos actividades de flujo de trabajo anteriores se basa en este participante de persistencia personalizado.  
  
```  
public class SqlWorkflowInstanceStorePromotionBehavior :  
             SqlWorkflowInstanceStoreBehavior, IServiceBehavior  
{  
        public void Promote(string name, IEnumerable<string> promoteAsSqlVariant,  
                            IEnumerable<string> promoteAsBinary)  
  
}  
```  
  
 Esta biblioteca de clases también contiene la implementación `ConfigurationElement` para `SqlWorkflowInstanceStorePromotionElement` y un participante de persistencia personalizado utilizado por las actividades de promoción anteriores.  
  
### <a name="propertypromotionactivitysqlsample"></a>PropertyPromotionActivitySQLSample  
 Este archivo SQL crea una vista `[dbo].[CounterService]` además de la vista `[InstancePromotedProperties]` ven para consultar todas las instancias que un conjunto de Promoción de CounterService.  
  
> [!IMPORTANT]
>  Puede que los ejemplos ya estén instalados en su equipo. Compruebe el siguiente directorio (predeterminado) antes de continuar:  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Si no existe este directorio, vaya a la página [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) [Ejemplos de Windows Communication Foundation (WCF) y Windows Workflow Foundation (WF) para .NET Framework 4] para descargar todos los ejemplos de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] y [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Este ejemplo se encuentra en el siguiente directorio:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Persistence\PropertyPromotionActivity`  
  
## <a name="see-also"></a>Vea también  
 [Ejemplos de persistencia y el hospedaje de AppFabric](http://go.microsoft.com/fwlink/?LinkId=193961)
