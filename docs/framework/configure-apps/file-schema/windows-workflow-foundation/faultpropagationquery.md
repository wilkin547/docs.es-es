---
description: 'Más información acerca de: <faultPropagationQuery>'
title: <faultPropagationQuery>
ms.date: 03/30/2017
ms.topic: reference
ms.assetid: 4fb5c2b1-3dad-4eca-9c7f-3efb51899813
ms.openlocfilehash: 08786bfa66d74f5f29353c4d6a86a2abd34df8f9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748705"
---
# \<faultPropagationQuery>

Representa una consulta que se usa para realizar el seguimiento del control de los errores que se producen dentro de una actividad.  Este evento se produce cada vez que un FaultHandler procesa un error. Debería usar tal consulta para realizar el seguimiento del control de errores que se producen dentro de una actividad. La consulta es necesaria que un participante del seguimiento se suscriba a los registros de propagación de errores.

 Para obtener más información sobre las consultas de Perfil de seguimiento, consulte [perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md).

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.ServiceModel>**](system-servicemodel-of-workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<tracking>**](tracking.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<trackingProfile>**](trackingprofile.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<workflow>**](workflow.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<faultPropagationQueries>**](faultpropagationqueries.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<faultPropagationQuery>**

## <a name="syntax"></a>Sintaxis

```xml
<tracking>
  <trackingProfile name="Name">
    <workflow>
      <faultPropagationQueries>
        <faultPropagationQuery activityName="String"
                               faultHandlerActivityName="String" />
      </faultPropagationQueries>
    </workflow>
  </trackingProfile>
</tracking>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|activityName|Cadena que especifica el nombre de la actividad del controlador de errores que propagó el error. El valor predeterminado es *, que indica que los registros de propagación de errores se devuelven para todas las actividades.|
|faultHandlerActivityName|Una cadena que especifica el nombre de la actividad que originó el error.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|[\<faultPropagationQueries>](faultpropagationqueries.md)|Representa una lista de elementos de configuración que se utilizan para realizar el seguimiento del control de errores que se producen dentro de una actividad.  Este evento se produce cada vez que un FaultHandler procesa un error.|

## <a name="see-also"></a>Vea también

- <xref:System.ServiceModel.Activities.Tracking.Configuration.FaultPropagationQueryElement?displayProperty=nameWithType>
- <xref:System.Activities.Tracking.FaultPropagationQuery?displayProperty=nameWithType>
- [Seguimiento y traza del flujo de trabajo](../../../windows-workflow-foundation/workflow-tracking-and-tracing.md)
- [Perfiles de seguimiento](../../../windows-workflow-foundation/tracking-profiles.md)
