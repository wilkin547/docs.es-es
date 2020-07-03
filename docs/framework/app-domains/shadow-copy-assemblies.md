---
title: Copias sombra de ensamblados
description: Obtenga información sobre las instantáneas de ensamblados en .NET, que permiten que los ensamblados que se usan en un dominio de aplicación se puedan actualizar sin descargar el dominio de aplicación.
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], shadow copying
- application domains, shadow copying assemblies
- shadow copying assemblies
ms.assetid: de8b8759-fca7-4260-896b-5a4973157672
ms.openlocfilehash: a7ff72763dd26dbc50cd37e070c2d25ababa00f3
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104560"
---
# <a name="shadow-copying-assemblies"></a>Copias sombra de ensamblados

Las instantáneas permiten que los ensamblados que se usan en un dominio de aplicación se actualicen sin descargar el dominio de aplicación. Esto es especialmente útil para las aplicaciones que tienen que estar disponibles continuamente, como los sitios de ASP.NET.

> [!IMPORTANT]
> En las aplicaciones de la Tienda Windows 8.x no se admite la generación de instantáneas.

Common Language Runtime bloquea el archivo de ensamblado al cargar el ensamblado, por lo que no se puede actualizar el archivo hasta que se descarga el ensamblado. La única manera de descargar un ensamblado de un dominio de aplicación es descargar el dominio de aplicación, por lo que en circunstancias normales, no se puede actualizar un ensamblado en el disco hasta que todos los dominios de aplicación que lo están usando se descargan.

Cuando un dominio de aplicación se configura para realizar instantáneas de los archivos, los ensamblados de la ruta de acceso de la aplicación se copian a otra ubicación y se cargan desde esa ubicación. La instantánea está bloqueada, pero el archivo de ensamblado original está desbloqueado y se puede actualizar.

> [!IMPORTANT]
> Los únicos ensamblados de los que se pueden realizar instantáneas son los que se almacenan en el directorio de la aplicación o sus subdirectorios, y se especifican con las propiedades <xref:System.AppDomainSetup.ApplicationBase%2A> y <xref:System.AppDomainSetup.PrivateBinPath%2A> cuando se configura el dominio de aplicación. De los ensamblados almacenados en la caché global de ensamblados no se realizan instantáneas.

Este artículo contiene las siguientes secciones:

- En [Habilitar y usar instantáneas](#EnablingAndUsing) se describe el uso básico y las opciones disponibles para crear instantáneas.

- En [Rendimiento de inicio](#StartupPerformance) se describen los cambios que se realizan para crear instantáneas en .NET Framework 4 de cara a mejorar el rendimiento de inicio y cómo revertir al comportamiento de las versiones anteriores.

- En [Métodos obsoletos](#ObsoleteMethods) se describen los cambios realizados en las propiedades y los métodos que controlan las instantáneas en .NET Framework 2.0.

<a name="EnablingAndUsing"></a>

## <a name="enabling-and-using-shadow-copying"></a>Habilitar y usar instantáneas

Puede utilizar las propiedades de la clase <xref:System.AppDomainSetup> como se indica a continuación para configurar un dominio de aplicación y crear instantáneas:

- Habilite las instantáneas estableciendo la propiedad <xref:System.AppDomainSetup.ShadowCopyFiles%2A> como el valor de cadena `"true"`.

  De forma predeterminada, este ajuste hace que todos los ensamblados de la ruta de acceso de la aplicación se copien en una caché de descarga antes de cargarse. Se trata de la misma caché mantenida por Common Language Runtime para almacenar archivos descargados de otros equipos, y Common Language Runtime elimina automáticamente los archivos cuando dejan de ser necesarios.

- Si quiere, establezca una ubicación personalizada para los archivos de instantáneas con las propiedades <xref:System.AppDomainSetup.CachePath%2A> y <xref:System.AppDomainSetup.ApplicationName%2A>.

  La ruta de acceso base de la ubicación se forma concatenando la propiedad <xref:System.AppDomainSetup.ApplicationName%2A> a la propiedad <xref:System.AppDomainSetup.CachePath%2A> como un subdirectorio. Las instantáneas de los ensamblados se colocan en los subdirectorios de esta ruta, no en la ruta de acceso base.

  > [!NOTE]
  > Si no se establece la propiedad <xref:System.AppDomainSetup.ApplicationName%2A>, la propiedad <xref:System.AppDomainSetup.CachePath%2A> se ignora y se utiliza la caché de descarga. No se inicia ninguna excepción.

  Si especifica una ubicación personalizada, será usted el responsable de limpiar los directorios y los archivos copiados cuando dejen de ser necesarios. No se eliminan automáticamente.

  Hay varias razones por las que puede que le convenga establecer una ubicación personalizada para los archivos de instantáneas. Puede que le venga bien establecer una ubicación personalizada para los archivos de instantáneas si la aplicación genera un gran número de copias. La caché de descarga tiene un límite de tamaño, no de duración, por lo que es posible que Common Language Runtime trate de eliminar un archivo que todavía se esté usando. Otra razón para establecer una ubicación personalizada se da cuando los usuarios que ejecutan la aplicación no tienen acceso de escritura a la ubicación del directorio que Common Language Runtime utiliza para la caché de descarga.

- Si quiere, puede limitar los ensamblados de los que se toman instantáneas con la propiedad <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>.

  Al habilitar las instantáneas en un dominio de aplicación, el valor predeterminado es copiar todos los ensamblados en la ruta de acceso de la aplicación, es decir, en los directorios especificados por las propiedades <xref:System.AppDomainSetup.ApplicationBase%2A> y <xref:System.AppDomainSetup.PrivateBinPath%2A>. Puede limitar la copia a determinados directorios: para ello, cree una cadena que contenga solo los directorios de los que quiera crear instantáneas y asigne la cadena a la propiedad <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>. Separe los directorios con punto y coma. Solo se realizarán instantáneas de los ensamblados situados en los directorios seleccionados.

  > [!NOTE]
  > Si no asigna ninguna cadena a la propiedad <xref:System.AppDomainSetup.ShadowCopyDirectories%2A>, o si establece esta propiedad como `null`, se realizarán instantáneas de todos los ensamblados de los directorios especificados por las propiedades <xref:System.AppDomainSetup.ApplicationBase%2A> y <xref:System.AppDomainSetup.PrivateBinPath%2A>.

  > [!IMPORTANT]
  > Las rutas de acceso de directorio no deben contener ningún carácter de punto y coma, porque el punto y coma es el carácter delimitador. No hay ningún carácter de escape para el punto y coma.

<a name="StartupPerformance"></a>

## <a name="startup-performance"></a>Rendimiento de inicio

Cuando se inicia un dominio de aplicación que utiliza instantáneas, hay un retraso mientras las instantáneas del directorio de aplicación se copian al directorio de instantáneas, o se comprueba si ya están en esa ubicación. Antes de .NET Framework 4, todos los ensamblados se copiaban en un directorio temporal. Cada ensamblado se abría para comprobar el nombre del ensamblado y el nombre seguro se validaba. Se comprobaba cada ensamblado para saber si se actualizó más recientemente que la copia del directorio de instantáneas. Si es así, se copiaba al directorio de instantáneas. Por último, se descartaban las copias temporales.

A partir de .NET Framework 4, el comportamiento de inicio predeterminado consiste en comparar directamente la fecha y la hora de cada archivo de ensamblado del directorio de aplicación con la fecha y la hora de la copia situada en el directorio de instantáneas. Si el ensamblado se ha actualizado, se copiará con el mismo procedimiento que en las versiones anteriores de .NET Framework. Si no, se cargará la copia del directorio de instantáneas.

La mejora del rendimiento resultante es mayor en las aplicaciones en las que los ensamblados no cambian con frecuencia y, normalmente, los cambios se producen en un pequeño subconjunto de ensamblados. Si la mayoría de los ensamblados de una aplicación cambia con frecuencia, el nuevo comportamiento predeterminado puede provocar una regresión del rendimiento. Puede restaurar el comportamiento de inicio de las versiones anteriores de .NET Framework. Para ello, agregue el [elemento \<shadowCopyVerifyByTimestamp>](../configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md) al archivo de configuración, con `enabled="false"`.

<a name="ObsoleteMethods"></a>

## <a name="obsolete-methods"></a>Métodos obsoletos

La clase <xref:System.AppDomain> tiene varios métodos, como <xref:System.AppDomain.SetShadowCopyFiles%2A> y <xref:System.AppDomain.ClearShadowCopyPath%2A>, que pueden utilizarse para controlar la creación de instantáneas en un dominio de aplicación, pero estos métodos se marcaron como obsoletos en la versión 2.0 de .NET Framework. La forma recomendada de configurar un dominio de aplicación es utilizar las propiedades de la clase <xref:System.AppDomainSetup>.

## <a name="see-also"></a>Vea también

- <xref:System.AppDomainSetup.ShadowCopyFiles%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.CachePath%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.ApplicationName%2A?displayProperty=nameWithType>
- <xref:System.AppDomainSetup.ShadowCopyDirectories%2A?displayProperty=nameWithType>
- [Elemento \<shadowCopyVerifyByTimestamp>](../configure-apps/file-schema/runtime/shadowcopyverifybytimestamp-element.md)
