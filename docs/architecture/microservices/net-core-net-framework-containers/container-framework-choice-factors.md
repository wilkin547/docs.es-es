---
title: Tabla de decisiones. Versiones de .NET Framework para su uso con Docker
description: Arquitectura de microservicios de .NET para aplicaciones .NET en contenedor | Tabla de decisiones, versiones de .NET Framework para su uso con Docker
ms.date: 09/11/2018
ms.openlocfilehash: 96b2750e52d64b06444b7f87dea624879f37d3d7
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/30/2019
ms.locfileid: "68675822"
---
# <a name="decision-table-net-frameworks-to-use-for-docker"></a>Tabla de decisiones: versiones de .NET Framework para su uso con Docker

En la siguiente tabla de decisiones se resume si se debe usar .NET Framework o .NET Core. Recuerde que, para los contenedores de Linux, necesita hosts de Docker basados en Linux (máquinas virtuales o servidores) y, para los contenedores de Windows, necesita hosts de Docker basados en Windows Server (máquinas virtuales o servidores).

> [!IMPORTANT]
> Los equipos de desarrollo ejecutarán un host de Docker, ya sea Linux o Windows. Todos los microservicios relacionados que quiera ejecutar y probar juntos en una solución deberán ejecutarse en la misma plataforma de contenedor.

<table>
<thead>
<tr class="header">
<th><strong>Arquitectura/tipo de aplicación</strong></th>
<th><strong>Contenedores de Linux</strong></th>
<th><strong>Contenedores de Windows</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Microservicios en contenedores</td>
<td>Núcleo de .NET</td>
<td>Núcleo de .NET</td>
</tr>
<tr class="even">
<td>Aplicación monolítica</td>
<td>Núcleo de .NET</td>
<td><p>.NET Framework</p>
<p>Núcleo de .NET</p></td>
</tr>
<tr class="odd">
<td>Rendimiento y escalabilidad líderes</td>
<td>Núcleo de .NET</td>
<td>Núcleo de .NET</td>
</tr>
<tr class="even">
<td>Migración de aplicación heredada de Windows Server ("brown-field") a contenedores</td>
<td>--</td>
<td>.NET Framework</td>
</tr>
<tr class="odd">
<td>Nuevo desarrollo basado en contenedor ("green-field")</td>
<td>Núcleo de .NET</td>
<td>Núcleo de .NET</td>
</tr>
<tr class="even">
<td>ASP.NET Core</td>
<td>Núcleo de .NET</td>
<td><p>.NET Core (recomendado)</p>
<p>.NET Framework</p></td>
</tr>
<tr class="odd">
<td>ASP.NET 4 (MVC 5, API web 2 y formularios Web Forms)</td>
<td>--</td>
<td>.NET Framework</td>
</tr>
<tr class="even">
<td>Servicios SignalR</td>
<td>.NET Core 2.1 o versiones posteriores</td>
<td><p>.NET Framework</p>
<p>.NET Core 2.1 o versiones posteriores</p></td>
</tr>
<tr class="odd">
<td>WCF, WF y otros marcos heredados</td>
<td>WCF en .NET Core (solo la biblioteca cliente de WCF)</td>
<td><p>.NET Framework</p>
<p>WCF en .NET Core (solo la biblioteca cliente de WCF)</p></td>
</tr>
<tr class="even">
<td>Consumo de servicios de Azure</td>
<td><p>Núcleo de .NET</p>
<p>(finalmente todos los servicios de Azure proporcionarán el SDK de cliente para .NET Core)</p></td>
<td><p>.NET Framework</p>
<p>Núcleo de .NET</p>
<p>(finalmente todos los servicios de Azure proporcionarán el SDK de cliente para .NET Core)</p></td>
</tr>
</tbody>
</table>

>[!div class="step-by-step"]
>[Anterior](net-framework-container-scenarios.md)
>[Siguiente](net-container-os-targets.md)
