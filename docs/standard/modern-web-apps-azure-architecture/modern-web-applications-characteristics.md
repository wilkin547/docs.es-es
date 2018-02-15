---
title: "Características de aplicaciones web modernas"
description: "Diseñar aplicaciones Web modernas con ASP.NET Core y Azure | características de aplicaciones web modernas"
author: ardalis
ms.author: wiwagn
ms.date: 10/06/2017
ms.prod: .net-core
ms.technology: dotnet-docker
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: ecef23870ac547f4b4066628da71f8af98c91b27
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="characteristics-of-modern-web-applications"></a>Características de aplicaciones Web modernas

> "… las características de un diseño adecuado, conlleva económica. Este enfoque es arduo, pero continúa lleve a cabo correctamente."  
> _\- Dennis Ritchie_

## <a name="summary"></a>Resumen

Las aplicaciones web modernas tienen las expectativas del usuario superior y mayor demanda que nunca. Las aplicaciones web de hoy en día deben estar disponibles 24/7 desde cualquier lugar del mundo y se puede usar desde prácticamente cualquier dispositivo o tamaño de la pantalla. Aplicaciones Web deben ser segura, flexible y escalable para satisfacer los picos de demanda. Cada vez más, los escenarios complejos deben controlarse con experiencias de usuario enriquecida creadas en el cliente con JavaScript y comunicarse de forma eficaz a través de las API web.

ASP.NET Core está optimizado para aplicaciones web modernas y escenarios de hospedaje en la nube. Su diseño modular permite que las aplicaciones que dependen sólo aquellas características que realmente utilizan, mejorar la seguridad de la aplicación y el rendimiento al reducir los requisitos de recursos de host.

## <a name="reference-application-eshoponweb"></a>Referencia de aplicación: eShopOnWeb

Esta guía incluye una aplicación de referencia, *eShopOnWeb*, que muestran algunos de los principios y las recomendaciones. La aplicación es una tienda en línea simple que admite la exploración a través de un catálogo de camisetas, tazas de café y otros elementos de marketing. La aplicación de referencia es deliberadamente sencilla para que sea fácil de entender.

**Figura 2-1.** eShopOnWeb

![](./media/image2-1.png)

> ### <a name="reference-application"></a>Aplicación de referencia
> - **eShopOnWeb**  
> <https://github.com/dotnet/eShopOnWeb>

## <a name="cloud-hosted-and-scalable"></a>Hospedado en la nube y escalable

ASP.NET Core está optimizado para la nube (nube pública, en la nube privada, cualquier nube) porque está bajo de memoria y de alto rendimiento. La menor superficie de aplicaciones de ASP.NET Core significa que puede hospedar varias de ellas en el mismo hardware, y se paga por menos recursos cuando con el pago a medida que vaya a servicios de hospedaje en nube. El rendimiento mayor significa que puede servir a más clientes desde una aplicación que tiene el mismo hardware, reduciendo así la necesidad de invertir en servidores y la infraestructura de hospedaje.

## <a name="cross-platform"></a>Multiplataforma

ASP.NET Core multiplataforma y se pueden ejecutar en Linux y Mac OS, así como de Windows. Esto abrirá muchas opciones nuevas para el desarrollo y la implementación de aplicaciones compiladas con ASP.NET Core. Contenedores de docker, que normalmente se ejecutan Linux hoy en día, pueden hospedar aplicaciones ASP.NET Core, lo que les permite sacar partido de las ventajas de [contenedores y microservicios](../microservices-architecture/index.md).

## <a name="modular-and-loosely-coupled"></a>Acoplamiento flexible y modular

Paquetes de NuGet son objetos de primera clase en .NET Core y ASP.NET Core aplicaciones se componen de muchas bibliotecas a través de NuGet. Este nivel de detalle de la funcionalidad ayuda a garantizar aplicaciones solo dependen e implementación la funcionalidad que realmente necesitan, lo que reduce su área de superficie de vulnerabilidad de seguridad y la superficie de.

ASP.NET Core también totalmente compatible con la inserción de dependencias, tanto internamente como en el nivel de aplicación. Interfaces pueden tener varias implementaciones que pueden intercambiarse según sea necesario. Inyección de dependencia permite a flexible par a esas interfaces, lo que facilita su ampliar, mantener y probar las aplicaciones.

## <a name="easily-tested-with-automated-tests"></a>Probar fácilmente con las pruebas automatizadas

Las aplicaciones de ASP.NET Core admiten pruebas unitarias y el acoplamiento flexible y la compatibilidad con inyecciones de dependencia facilita la intercambiar problemas de infraestructura con implementaciones falsas para fines de prueba. ASP.NET Core también se suministra un TestServer que puede usarse para aplicaciones de host en la memoria. Pruebas funcionales, a continuación, pueden realizar solicitudes a este servidor en memoria, llevar a cabo la pila de aplicación completo (incluido el software intermedio, enrutamiento, el enlace de modelos, filtros, etc.) y recibir una respuesta en una fracción del tiempo necesario para hospedar la aplicación en un servidor real y realizar solicitudes a través de la capa de red. Estas pruebas son especialmente fáciles de escribir y útil para las API, que son cada vez más importante en aplicaciones web modernas.

## <a name="traditional-and-spa-behaviors-supported"></a>Tradicionales y los comportamientos SPA compatibles

Aplicaciones web tradicionales han implicado poco comportamiento del lado del cliente, pero en su lugar se basaban en el servidor para todas las actualizaciones de la aplicación puede que deba realizar, consultas y navegación. Cada nueva operación realizada por el usuario se puede convertir en una nueva solicitud de web, con lo que se va a una recarga de página completa en el explorador del usuario final. Marcos de trabajo Model-View-Controller (MVC) clásico normalmente siguen este enfoque, con cada nueva solicitud correspondiente a una acción de otro controlador, que a su vez podría trabajar con un modelo y devolver una vista. Algunas operaciones individuales en una página determinada pueden mejorarse con funcionalidad de AJAX (JavaScript asincrónico y XML), pero la arquitectura global de la aplicación utiliza muchos distintas vistas MVC y los puntos de conexión de dirección URL.

Las aplicaciones de página única (SPAs), por el contrario, implican muy pocas carga de página generada dinámicamente de servidor (si existe). Muchos SPAs se inicializan en un archivo HTML estático que carga las bibliotecas de JavaScript necesarias para iniciar y ejecutar la aplicación. Estas aplicaciones hacen un uso intensivo de las API web para sus necesidades de datos y pueden proporcionan que mucho más enriquecida usuario experimente.

Muchas aplicaciones web implican una combinación de comportamientos de las aplicaciones de web tradicionales (normalmente para el contenido) y SPAs (durante la interactividad). Es compatible con ASP.NET Core MVC y las API web de la misma aplicación, con el mismo conjunto de herramientas y subyacente bibliotecas de framework.

## <a name="simple-development-and-deployment"></a>Implementación y desarrollo simple

Las aplicaciones de ASP.NET Core se pueden escribir con editores de texto simple y las interfaces de línea de comandos o entornos de desarrollo completos como Visual Studio. Aplicaciones monolíticas normalmente se implementan en un solo punto de conexión. Las implementaciones pueden automatizarse fácilmente para que se realice como parte de una integración continua (CI) y la canalización de la entrega continua (CD). Además de las herramientas tradicionales de CI/CD, Windows Azure tiene compatibilidad integrada para repositorios git y se pueden implementar automáticamente actualizaciones cuando que se realizan en una rama de git especificado o una etiqueta.

## <a name="traditional-aspnet-and-web-forms"></a>ASP.NET tradicional y formularios Web Forms

Además de núcleo de ASP.NET, ASP.NET tradicional 4.x sigue siendo una plataforma sólida y confiable para compilar aplicaciones web. Es compatible con ASP.NET MVC y API Web de modelos de desarrollo, así como formularios Web Forms, que es adecuada para el desarrollo de aplicaciones enriquecido basado en páginas y características de un ecosistema de componentes de terceros enriquecido. Windows Azure tiene mayor compatibilidad de enfoque para las aplicaciones de ASP.NET 4.x y muchos desarrolladores están familiarizados con esta plataforma.

> ### <a name="references--modern-web-applications"></a>Referencias: aplicaciones Web modernas
> - **Introducción a ASP.NET Core**  
> <https://docs.microsoft.com/aspnet/core/>
> - **Seis clave ventajas de ASP.NET Core que facilitan diferentes y mejor**  
> <https://blog.trigent.com/six-key-benefits-of-asp-net-core-1-0-which-make-it-different-better/>
> - **Pruebas de ASP.NET Core**  
> <https://docs.microsoft.com/aspnet/core/testing/>

>[!div class="step-by-step"]
[Previous] (index.md) [Next] (choose-between-traditional-web-and-single-page-apps.md)
