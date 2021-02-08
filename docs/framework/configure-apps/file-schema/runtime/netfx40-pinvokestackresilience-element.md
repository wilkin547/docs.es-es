---
description: 'Más información acerca de: <NetFx40_PInvokeStackResilience elemento>'
title: Elemento <NetFx40_PInvokeStackResilience>
ms.date: 03/30/2017
helpviewer_keywords:
- <NetFx40_PInvokeStackResilience> element
- NetFx40_PInvokeStackResilience element
ms.assetid: 39fb1588-72a4-4479-af74-0605233b68bd
ms.openlocfilehash: 59e2a5845868ebfa186344c9a731871739a29c47
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99782304"
---
# <a name="netfx40_pinvokestackresilience-element"></a>\<NetFx40_PInvokeStackResilience> (Elemento)

Especifica si el runtime corrige automáticamente las declaraciones de invocación de plataforma incorrectas en tiempo de ejecución, a costa de transiciones más lentas entre código administrado y código no administrado.

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<runtime>**](runtime-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;**\<NetFx40_PInvokeStackResilience>**  

## <a name="syntax"></a>Sintaxis

```xml
<NetFx40_PInvokeStackResilience  enabled="1|0"/>
```

## <a name="attributes-and-elements"></a>Atributos y elementos

En las siguientes secciones se describen los atributos, los elementos secundarios y los elementos primarios.

### <a name="attributes"></a>Atributos

|Atributo|Descripción|
|---------------|-----------------|
|`enabled`|Atributo necesario.<br /><br /> Especifica si el tiempo de ejecución detecta declaraciones de invocación de plataforma incorrectas y corrige automáticamente la pila en tiempo de ejecución en las plataformas de 32 bits.|

## <a name="enabled-attribute"></a>Atributo enabled

|Value|Descripción|
|-----------|-----------------|
|`0`|El motor en tiempo de ejecución utiliza la arquitectura de serialización de interoperabilidad más rápida incluida en el .NET Framework 4, que no detecta ni corrige las declaraciones de invocación de plataforma incorrectas. Este es el valor predeterminado.|
|`1`|El motor en tiempo de ejecución utiliza transiciones más lentas que detectan y corrigen declaraciones de invocación de plataforma incorrectas.|

### <a name="child-elements"></a>Elementos secundarios

Ninguno.

### <a name="parent-elements"></a>Elementos primarios

|Elemento|Descripción|
|-------------|-----------------|
|`configuration`|Elemento raíz de cada archivo de configuración usado por las aplicaciones de Common Language Runtime y .NET Framework.|
|`runtime`|Contiene información sobre las opciones de inicialización del motor en tiempo de ejecución.|

## <a name="remarks"></a>Observaciones

Este elemento le permite intercambiar el cálculo de referencias de interoperabilidad más rápido para la resistencia en tiempo de ejecución con declaraciones de invocación de plataforma incorrectas.

A partir de la .NET Framework 4, una arquitectura de serialización de interoperabilidad simplificada proporciona una mejora significativa del rendimiento para las transiciones de código administrado a código no administrado. En versiones anteriores del .NET Framework, la capa de serialización detectaba declaraciones de invocación de plataforma incorrectas en las plataformas de 32 bits y corrige automáticamente la pila. La nueva arquitectura de cálculo de referencias elimina este paso. Como resultado, las transiciones son muy rápidas, pero una declaración incorrecta de invocación de plataforma puede producir un error en el programa.

Para facilitar la detección de declaraciones incorrectas durante el desarrollo, se ha mejorado la experiencia de depuración de Visual Studio. El Asistente para la depuración administrada (MDA) de [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md) le notifica las declaraciones de invocación de plataforma incorrectas cuando la aplicación se ejecuta con el depurador asociado.

Para solucionar los escenarios en los que la aplicación usa componentes que no se pueden volver a compilar y que tienen declaraciones de invocación de plataforma incorrectas, puede utilizar el `NetFx40_PInvokeStackResilience` elemento. Al agregar este elemento al archivo de configuración de `enabled="1"` la aplicación, se opta por un modo de compatibilidad con el comportamiento de las versiones anteriores del .NET Framework, a costa de transiciones más lentas. Los ensamblados compilados con versiones anteriores del .NET Framework se incorporan automáticamente a este modo de compatibilidad y no necesitan este elemento.

## <a name="configuration-file"></a>Archivo de configuración

Este elemento solo se puede usar en el archivo de configuración de la aplicación.

## <a name="example"></a>Ejemplo

En el ejemplo siguiente se muestra cómo optar por aumentar la resistencia frente a las declaraciones de invocación de plataforma incorrectas para una aplicación, a costa de transiciones más lentas entre código administrado y no administrado.

```xml
<configuration>
   <runtime>
      <NetFx40_PInvokeStackResilience enabled="1"/>
   </runtime>
</configuration>
```

## <a name="see-also"></a>Vea también

- [Esquema de la configuración de Common Language Runtime](index.md)
- [Esquema de los archivos de configuración](../index.md)
- [pInvokeStackImbalance](../../../debug-trace-profile/pinvokestackimbalance-mda.md)
