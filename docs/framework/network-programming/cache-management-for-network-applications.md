---
title: Administración de la memoria caché para aplicaciones de red
ms.date: 03/30/2017
helpviewer_keywords:
- cache [.NET Framework], network applications
- network resources, caching
- Internet, caching
ms.assetid: fc258a40-f370-434f-ae09-4a8cb11ddaeb
ms.openlocfilehash: 7e131963999db3e3d5e0e6f3fa110da36e6452a1
ms.sourcegitcommit: 289e06e904b72f34ac717dbcc5074239b977e707
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2019
ms.locfileid: "71048877"
---
# <a name="cache-management-for-network-applications"></a>Administración de la memoria caché para aplicaciones de red
Este tema y los temas secundarios relacionados describen el almacenamiento en caché de los recursos obtenidos mediante las clases <xref:System.Net.WebClient>, <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest> y <xref:System.Net.FtpWebRequest>.  
  
 Una memoria caché proporciona almacenamiento temporal de recursos solicitados por una aplicación. Si una aplicación solicita el mismo recurso más de una vez, este se puede devolver desde la memoria caché, con lo que se evita la sobrecarga de volver a solicitarlo desde el servidor. El almacenamiento en caché puede mejorar el rendimiento de la aplicación al reducir el tiempo necesario para obtener un recurso solicitado. El almacenamiento en caché también puede disminuir el tráfico de red al reducir el número de viajes al servidor. Aunque el almacenamiento en caché mejora el rendimiento, aumenta el riesgo de que el recurso devuelto a la aplicación esté obsoleto, lo que significa que no es idéntico al recurso que habría enviado el servidor si no se estuviera usando el almacenamiento en caché.  
  
 El almacenamiento en caché puede permitir que usuarios o procesos no autorizados lean datos confidenciales. Se puede recuperar una respuesta autenticada almacenada en caché sin ninguna autorización adicional. Si el almacenamiento en caché está habilitado, cambie <xref:System.Net.WebRequest.CachePolicy%2A> a <xref:System.Net.Cache.RequestCacheLevel.BypassCache> o <xref:System.Net.Cache.RequestCacheLevel.NoCacheNoStore> para deshabilitar el almacenamiento en caché de esta solicitud.  
  
 Por motivos de seguridad, el almacenamiento en caché **no** se recomienda para escenarios de nivel intermedio.  
  
## <a name="in-this-section"></a>En esta sección  
 [Directiva de caché](cache-policy.md)  
 Explica qué es una directiva de caché y cómo definirla.  
  
 [Directivas de caché basadas en la ubicación](location-based-cache-policies.md)  
 Define cada tipo de directiva de caché basada en la ubicación disponible para recursos de protocolo de transferencia de hipertexto (http y https).  
  
 [Directivas de caché de duración definida](time-based-cache-policies.md)  
 Describe los criterios que pueden usarse para personalizar una directiva de caché basada en el tiempo.  
  
 [Configurar el almacenamiento en caché de las aplicaciones de red](configuring-caching-in-network-applications.md)  
 Explica cómo crear directivas de caché mediante programación y solicitudes que usen el almacenamiento en caché.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Net.Cache>  
 Define los tipos y las enumeraciones usados para definir directivas de caché para los recursos obtenidos mediante las clases <xref:System.Net.WebRequest>, <xref:System.Net.HttpWebRequest> y <xref:System.Net.FtpWebRequest>.
