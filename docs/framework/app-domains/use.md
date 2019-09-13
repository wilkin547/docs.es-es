---
title: Utilizar dominios de aplicación
ms.date: 03/30/2017
helpviewer_keywords:
- application domains, about
- common language runtime, application domains
- runtime, application domains
ms.assetid: c6d99815-e022-4d2c-9420-1d7ab5b9d504
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad05d005ece4a52e2df0dbb7e044522db58f1787
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2019
ms.locfileid: "70971859"
---
# <a name="using-application-domains"></a>Utilizar dominios de aplicación
Los dominios de aplicación proporcionan una unidad de aislamiento para Common Language Runtime. Se crean y se ejecutan dentro de un proceso. Los dominios de aplicación suele crearlos un host en tiempo de ejecución, que es una aplicación encargada de cargar el tiempo de ejecución en un proceso y ejecutar el código de usuario dentro de un dominio de aplicación. El host en tiempo de ejecución crea un proceso y un dominio de aplicación predeterminado y ejecuta el código administrado dentro de él. Entre los hosts en tiempo de ejecución se incluyen ASP.NET, Microsoft Internet Explorer y el shell de Windows.  
  
 En la mayoría de las aplicaciones, no es necesario que cree su propio dominio de aplicación, ya que el host en tiempo de ejecución crea automáticamente los dominios de aplicación necesarios. A pesar de ello, puede crear y configurar dominios de aplicación adicionales si su aplicación necesita aislar el código o usar y descargar archivos DLL.  
  
## <a name="in-this-section"></a>En esta sección  
 [Cómo: Crear un dominio de aplicación](../../../docs/framework/app-domains/how-to-create-an-application-domain.md)  
 Describe cómo crear mediante programación un dominio de aplicación.  
  
 [Cómo: Descargar un dominio de aplicación](../../../docs/framework/app-domains/how-to-unload-an-application-domain.md)  
 Describe cómo descargar mediante programación un dominio de aplicación.  
  
 [Cómo: Configurar un dominio de aplicación](../../../docs/framework/app-domains/how-to-configure-an-application-domain.md)  
 Proporciona una introducción a la configuración de un dominio de aplicación.  
  
 [Recuperar información de instalación de un dominio de aplicación](../../../docs/framework/app-domains/retrieve-setup-information.md)  
 Describe cómo recuperar información de instalación de un dominio de aplicación.  
  
 [Cómo: Cargar ensamblados en un dominio de aplicación](../../../docs/framework/app-domains/how-to-load-assemblies-into-an-application-domain.md)  
 Describe cómo cargar un ensamblado en un dominio de aplicación.  
  
 [Cómo: Obtener información sobre tipos y miembros desde un ensamblado](../reflection-and-codedom/get-type-member-information.md)  
 Describe cómo recuperar información sobre un ensamblado.  
  
 [Copias sombra de ensamblados](../../../docs/framework/app-domains/shadow-copy-assemblies.md)  
 Describe la manera en que la creación de instantáneas permite actualizaciones en los ensamblados mientras están en uso y cómo se configura la creación de instantáneas.  
  
 [Cómo: para recibir notificaciones de excepciones de primera oportunidad](../../../docs/framework/app-domains/how-to-receive-first-chance-exception-notifications.md)  
 Explica cómo se puede recibir una notificación de que se ha producido una excepción antes de que Common Language Runtime empiece a buscar controladores de excepciones.  
  
 [Resolver cargas de ensamblado](../../standard/assembly/resolve-loads.md)  
 Proporciona instrucciones sobre cómo usar el evento <xref:System.AppDomain.AssemblyResolve?displayProperty=nameWithType> para resolver errores en la carga de ensamblados.  
  
## <a name="reference"></a>Referencia  
 <xref:System.AppDomain>  
 Representa un dominio de aplicación. Proporciona métodos para crear y controlar dominios de aplicación.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Ensamblados de .NET](../../standard/assembly/index.md)  
 Proporciona información general sobre las funciones que desempeñan los ensamblados.  
  
 [Programar con ensamblados](../../standard/assembly/program.md)  
 Describe cómo crear, firmar y establecer atributos en los ensamblados.  
  
 [Emitir métodos y ensamblados dinámicos](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)  
 Describe la creación de ensamblados dinámicos.  
  
 [Dominios de aplicación](../../../docs/framework/app-domains/application-domains.md)  
 Proporciona una introducción general a los conceptos de los dominios de aplicación.  
  
 [Información general de la reflexión](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Describe cómo usar la clase **Reflection** para obtener información sobre un ensamblado.
