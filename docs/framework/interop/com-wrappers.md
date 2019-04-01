---
title: Contenedores COM
ms.date: 03/30/2017
helpviewer_keywords:
- wrapper classes
- COM interop, COM wrappers
- COM wrappers
- COM, wrappers
- interoperation with unmanaged code, COM wrappers
- COM callable wrappers
ms.assetid: e56c485b-6b67-4345-8e66-fd21835a6092
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce15e0535bbd6bc67054c651a518f11cf9dd2ae1
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2019
ms.locfileid: "58410360"
---
# <a name="com-wrappers"></a>Contenedores COM
COM se diferencia del modelo de objetos de .NET Framework en varios aspectos importantes:  
  
-   Los clientes de objetos COM deben administrar la duración de los objetos; Common Language Runtime administra la duración de los objetos en su entorno.  
  
-   Los clientes de objetos COM detectan si un servicio está disponible solicitando una interfaz que proporciona ese servicio y obteniendo o no un puntero de interfaz. Los clientes de objetos .NET pueden obtener una descripción de la funcionalidad de un objeto mediante la reflexión.  
  
-   Los objetos .NET residen en memoria administrada por el entorno de ejecución de .NET Framework. El entorno de ejecución puede mover los objetos en la memoria por motivos de rendimiento y actualizar todas las referencias a los objetos que mueve. Los clientes no administrados, una vez obtenido un puntero a un objeto, se basan en el objeto para permanecer en la misma ubicación. Estos clientes no disponen de ningún mecanismo para tratar con un objeto cuya ubicación no es fija.  
  
 Para superar estas diferencias, el tiempo de ejecución proporciona clases contenedoras para que los clientes administrados y no administrados crean que están llamando a objetos dentro de su propio entorno. Cada vez que un cliente administrado llama a un método en un objeto COM, el tiempo de ejecución crea un [contenedor RCW](runtime-callable-wrapper.md). Los contenedores RCW analizan las diferencias entre los mecanismos de referencia administrados y no administrados, entre otras cosas. El tiempo de ejecución crea también un [contenedor CCW](com-callable-wrapper.md) para invertir el proceso, lo que permite a un cliente COM llamar sin problemas a un método en un objeto. NET. Como se muestra en la ilustración siguiente, la perspectiva del código de llamada determina la clase contenedora que crea el tiempo de ejecución.  
  
 ![Información general sobre los contenedores COM](./media/com-wrappers/bidirectional-com-overview.gif)  
  
 En la mayoría de los casos, el contenedor estándar RCW o CCW generado por el tiempo de ejecución proporciona la serialización adecuada para las llamadas que traspasan los límites entre COM y .NET Framework. Mediante atributos personalizados, puede ajustar el modo en que el tiempo de ejecución representa el código administrado y no administrado.  
  
## <a name="see-also"></a>Vea también
- [Interoperabilidad COM avanzada](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bd9cdfyx(v=vs.100))
- [Contenedor al que se puede llamar en tiempo de ejecución](runtime-callable-wrapper.md)
- [Contenedor CCW (COM callable wrapper)](com-callable-wrapper.md)
- [Personalización de contenedores estándar](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/h7hx9abd(v=vs.100))
- [Cómo: Personalizar contenedores RCW](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/56kh4hy7(v=vs.100))
