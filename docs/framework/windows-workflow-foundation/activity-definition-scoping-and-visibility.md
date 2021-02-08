---
description: 'Más información sobre: ámbito y visibilidad de la definición de actividad'
title: Ámbito y visibilidad de la definición de actividad
ms.date: 03/30/2017
ms.assetid: ccdffa07-9503-4eea-a61b-17f1564368b7
ms.openlocfilehash: ab779fe36473a8888ee0fb0c1b94f1ea6324f991
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787973"
---
# <a name="activity-definition-scoping-and-visibility"></a>Ámbito y visibilidad de la definición de actividad

El ámbito y visibilidad de la definición de actividad,  como el ámbito y la visibilidad de un objeto, es la capacidad de otros objetos o actividades de obtener acceso a los miembros de la actividad. Las siguientes implementaciones realizan la definición de actividad:  
  
1. Al determinar los miembros (<xref:System.Activities.Argument>, objetos <xref:System.Activities.Variable> y <xref:System.Activities.ActivityDelegate>, y actividades secundarias) una actividad se expone a sus usuarios.  
  
2. Implementar la lógica de ejecución de la actividad.  
  
 La implementación puede implicar a miembros que no se exponen a los usuarios de la actividad, pero se trata más bien de detalles de la implementación.  Similar a la definición de tipo, el modelo de actividad permite a un autor calificar la visibilidad de un miembro de la actividad con respecto a la definición de la actividad que es definida.  Esta visibilidad rige aspectos de uso de los miembros, como el ámbito de los datos.  
  
## <a name="scope"></a>Ámbito  

 Además del ámbito de datos, la visibilidad del modelo de actividad puede restringir el acceso a otros aspectos de la actividad, como validación, depuración, seguimiento o traza. Las propiedades de ejecución utilizan la visibilidad y el ámbito para restringir las características de ejecución a un ámbito determinado de la definición. Las raíces secundarias utilizan la visibilidad y el ámbito para restringir el estado capturado por <xref:System.Activities.Statements.CompensableActivity> al ámbito de definición en la que se utilizan las actividades compensables.  
  
## <a name="definition-and-usage"></a>Definición y uso  

 Un flujo de trabajo se escribe creando nuevas actividades heredando de las clases de actividad base y usando las actividades de la [biblioteca de actividades integrada](net-framework-4-5-built-in-activity-library.md). Para utilizar una actividad, el autor de actividad debe configurar la visibilidad de cada componente de su definición.  
  
### <a name="activity-members"></a>Miembros de actividad  

 El modelo de actividad define los argumentos, variables, delegados y actividades secundarias que la actividad pone a disposición de los usuarios. Cada uno de estos miembros se puede declarar como `public` o `private`. El usuario de la actividad configura los miembros públicos, mientras que los miembros `private` utilizan una implementación corregida por el autor de actividad. Las reglas de visibilidad del ámbito de datos son las siguientes:  
  
1. Los miembros públicos y los miembros públicos de actividades secundarias públicas pueden hacer referencia a las variables públicas.  
  
2. Los miembros privados y los miembros públicos de actividades de  secundarias públicas pueden hacer referencia a argumentos y variables privadas.  
  
 Un miembro que puede ser establecido por el usuario de una actividad nunca se debería hacer privado.  
  
### <a name="authoring-models"></a>Modelos de creación  

 Las actividades personalizadas se definen utilizando <xref:System.Activities.NativeActivity>, <xref:System.Activities.Activity>, <xref:System.Activities.CodeActivity>o <xref:System.Activities.AsyncCodeActivity>. Las actividades que derivan de estas clases pueden exponer diferentes tipos de miembro con visibilidades diferentes.  
  
#### <a name="nativeactivity"></a>NativeActivity  

 Las actividades que derivan de <xref:System.Activities.NativeActivity> tienen un comportamiento escrito en el código imperativo y se pueden definir opcionalmente utilizando las actividades existentes. Al derivar actividades desde <xref:System.Activities.NativeActivity>, se permite acceso a todas las características expuestas por el runtime. Cualquier miembro de este tipo de actividad se puede definir utilizando visibilidad pública o  privada, excepto los argumentos, que solo se pueden declarar como `public`.  
  
 Los miembros de clases derivados de <xref:System.Activities.NativeActivity> se declaran al runtime utilizando el struct <xref:System.Activities.NativeActivityMetadata> pasado al método <xref:System.Activities.NativeActivity.CacheMetadata%2A>.  
  
#### <a name="activity"></a>Actividad  

 Las actividades creadas utilizando <xref:System.Activities.Activity> tienen un comportamiento que es diseñado estrictamente al componer otras actividades. La clase <xref:System.Activities.Activity> tiene una implementación de actividad secundaria, obtenida por el runtime al usar <xref:System.Activities.Activity.Implementation%2A>. Una actividad que deriva de <xref:System.Activities.Activity> puede definir los argumentos públicos, variables públicas, ActivityDelegates importados y Activities importadas.  
  
 LAs ActivityDelegates y Activities importadas se declaran como elementos secundarios públicos de la actividad, pero no pueden ser programadas directamente por la actividad. Esta información se utiliza durante la validación para evitar ejecutar las validaciones orientadas al elemento primario en las ubicaciones donde la actividad nunca se ejecutará. Además, los elementos secundarios importados, como los elementos secundarios públicos, pueden ser referenciados y programados por la implementación de la actividad. Esto significa que una actividad que importa una actividad llamada Activity1 puede contener una <xref:System.Activities.Statements.Sequence> en su implementación que programa la Activity1.  
  
#### <a name="codeactivity-asynccodeactivity"></a>CodeActivity/ AsyncCodeActivity  

 Esta clase base se utiliza para crear el comportamiento en código imperativo. Las actividades que derivan de esta clase solo tienen acceso a los argumentos que exponen. Esto significa que los únicos miembros que estas actividades pueden exponer son los argumentos públicos. Ningún otro miembro o visibilidad se aplican a estas actividades.  
  
#### <a name="summary-of-visibilities"></a>Resumen de visibilidades  

 En la siguiente tabla se resume la información anterior de esta sección.  
  
|Tipo de miembro|NativeActivity|Actividad|CodeActivity/ AsyncCodeActivity|  
|-----------------|--------------------|--------------|--------------------------------------|  
|Argumentos|Público/ privado|Público|no aplicable|  
|variables|Público/ privado|Público|no aplicable|  
|Actividades secundarias|Público/ privado|Público, uno elemento secundario privado definido en Implementación.|no aplicable|  
|ActivityDelegates|Público/ privado|Público|no aplicable|  
  
 En general, un miembro que no puede ser establecido por el usuario de una actividad no se debería hacer público.  
  
### <a name="execution-properties"></a>Propiedades de ejecución  

 En algunos escenarios, es útil establecer el ámbito de una propiedad de ejecución determinada en los elementos secundarios públicos de una actividad. La colección <xref:System.Activities.ExecutionProperties> proporciona esta capacidad con el método <xref:System.Activities.ExecutionProperties.Add%2A>. Este método tiene un parámetro Boolean que indica si una propiedad determinada está en el ámbito de todos los elementos secundarios o simplemente de aquellos que son públicos. Si este parámetro está establecido en `true`, la propiedad solo será visible para los miembros públicos y los miembros públicos de sus elementos secundarios públicos.  
  
### <a name="secondary-roots"></a>Raíces secundarias  

 Una raíz secundaria es el mecanismo interno del runtime para administrar el estado de las actividades de compensación. Cuando <xref:System.Activities.Statements.CompensableActivity> ha terminado de ejecutarse, no se limpia su estado inmediatamente. En su lugar, el estado es mantenido por el runtime en una raíz secundaria hasta que el episodio de compensación se haya completado. Los entornos de ubicación capturados con la raíz secundaria corresponden al ámbito de definición en la que se utiliza la actividad Compensable.
