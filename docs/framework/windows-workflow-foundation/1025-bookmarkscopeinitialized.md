---
title: 1025 - BookmarkScopeInitialized
ms.date: 03/30/2017
ms.assetid: 63584434-e709-471d-9e96-97d3d99e70d6
ms.openlocfilehash: ddc9b48120b9d31f71bfc99fff19ef252b08e295
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33509592"
---
# <a name="1025---bookmarkscopeinitialized"></a>1025 - BookmarkScopeInitialized
## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1025|  
|Palabras clave|WFRuntime|  
|Nivel|Detallado|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  
 Indica que se ha inicializado un BookmarkScope.  
  
## <a name="message"></a>Mensaje  
 El objeto BookmarkScope con TemporaryId: '%1' se ha inicializado con el id.: '%2'.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|TemporaryId|xs:string|Identificador temporal del marcador.|  
|InitializedId|xs:string|Identificador inicializado del marcador.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
