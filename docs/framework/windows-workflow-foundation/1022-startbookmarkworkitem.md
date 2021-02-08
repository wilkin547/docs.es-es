---
description: 'Más información acerca de: 1022-StartBookmarkWorkItem'
title: 1022 - StartBookmarkWorkItem
ms.date: 03/30/2017
ms.assetid: 4415fbdb-0329-4019-803f-aea66e75f3da
ms.openlocfilehash: 37d1ec1216df26a928b39189ca299dbb5b6c3d4b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792835"
---
# <a name="1022---startbookmarkworkitem"></a>1022 - StartBookmarkWorkItem

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1022|  
|Palabras clave|WFRuntime|  
|Nivel|Verbose|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que un BookmarkWorkItem está iniciando la ejecución.  
  
## <a name="message"></a>Message  

 Iniciando la ejecución de un BookmarkWorkItem para la actividad ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.  BookmarkName: %4, BookmarkScope: %5.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Actividad|xs:string|El nombre de tipo de la actividad.|  
|DisplayName|xs:string|El nombre para mostrar de la actividad.|  
|InstanceId|xs:string|La identificación de instancia de la actividad.|  
|BookmarkName|xs:string|Nombre del marcador.|  
|BookmarkScope|xs:string|Ámbito del marcador.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
