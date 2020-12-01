---
title: Utilizar dominios de aplicación
description: Los dominios de aplicación, que proporcionan una unidad de aislamiento para Common Language Runtime (CLR), se crean y se ejecutan dentro de un proceso.
ms.date: 03/30/2017
helpviewer_keywords:
- application domains, about
- common language runtime, application domains
- runtime, application domains
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
ms.openlocfilehash: 36bfc60a55c8b0374a7e542b590aa7c030ceaed6
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96272272"
---
# <a name="using-application-domains"></a>Utilizar dominios de aplicación

Los dominios de aplicación proporcionan una unidad de aislamiento para Common Language Runtime. Se crean y se ejecutan dentro de un proceso. Los dominios de aplicación suele crearlos un host en tiempo de ejecución, que es una aplicación encargada de cargar el tiempo de ejecución en un proceso y ejecutar el código de usuario dentro de un dominio de aplicación. El host en tiempo de ejecución crea un proceso y un dominio de aplicación predeterminado y ejecuta el código administrado dentro de él. Entre los hosts en tiempo de ejecución se incluyen ASP.NET, Microsoft Internet Explorer y el shell de Windows.  
  
En la mayoría de las aplicaciones, no es necesario que cree su propio dominio de aplicación, ya que el host en tiempo de ejecución crea automáticamente los dominios de aplicación necesarios. A pesar de ello, puede crear y configurar dominios de aplicación adicionales si su aplicación necesita aislar el código o usar y descargar archivos DLL.  
  
## <a name="in-this-section"></a>En esta sección  

[Cómo: Crear un dominio de aplicación](how-to-create-an-application-domain.md)  
Describe cómo crear mediante programación un dominio de aplicación.  
  
[Cómo: Descargar un dominio de aplicación](how-to-unload-an-application-domain.md)  
Describe cómo descargar mediante programación un dominio de aplicación.  
  
[Cómo: Configurar un dominio de aplicación](how-to-configure-an-application-domain.md)  
Proporciona una introducción a la configuración de un dominio de aplicación.  
  
[Recuperar información de instalación de un dominio de aplicación](retrieve-setup-information.md)  
Describe cómo recuperar información de instalación de un dominio de aplicación.  
  
[Cómo: Cargar ensamblados en un dominio de aplicación](how-to-load-assemblies-into-an-application-domain.md)  
Describe cómo cargar un ensamblado en un dominio de aplicación.  
  
[Cómo: Obtener información sobre tipos y miembros desde un ensamblado](../reflection-and-codedom/get-type-member-information.md)  
Describe cómo recuperar información sobre un ensamblado.  
  
[Copias sombra de ensamblados](shadow-copy-assemblies.md)  
Describe la manera en que la creación de instantáneas permite actualizaciones en los ensamblados mientras están en uso y cómo se configura la creación de instantáneas.  
  
[Cómo: para recibir notificaciones de excepciones de primera oportunidad](how-to-receive-first-chance-exception-notifications.md)  
Explica cómo se puede recibir una notificación de que se ha producido una excepción antes de que Common Language Runtime empiece a buscar controladores de excepciones.  
  
[Resolver cargas de ensamblado](../../standard/assembly/resolve-loads.md)  
Proporciona instrucciones sobre cómo usar el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> para resolver errores en la carga de ensamblados.  
  
## <a name="reference"></a>Referencia  

<xref:System.AppDomain>  
Representa un dominio de aplicación. Proporciona métodos para crear y controlar dominios de aplicación.  
  
## <a name="related-sections"></a>Secciones relacionadas  

[Ensamblados de .NET](../../standard/assembly/index.md)  
Proporciona información general sobre las funciones que desempeñan los ensamblados.  
  
[Programar con ensamblados](../../standard/assembly/index.md)  
Describe cómo crear, firmar y establecer atributos en los ensamblados.  
  
[Emitir métodos y ensamblados dinámicos](../reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
Describe la creación de ensamblados dinámicos.  
  
[Dominios de aplicación](application-domains.md)  
Proporciona una introducción general a los conceptos de los dominios de aplicación.  
  
[Información general de la reflexión](../reflection-and-codedom/reflection.md)  
Describe cómo usar la clase **Reflection** para obtener información sobre un ensamblado.
