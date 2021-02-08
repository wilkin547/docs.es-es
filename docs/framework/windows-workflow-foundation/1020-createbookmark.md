---
description: 'Más información acerca de: 1020-CreateBookmark'
title: 1020 - CreateBookmark
ms.date: 03/30/2017
ms.assetid: 4bee948d-816f-4803-85cc-3883b5e23d10
ms.openlocfilehash: 39796eaf68d9cb52e9faa2605fc21955a2c167ac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99792848"
---
# <a name="1020---createbookmark"></a>1020 - CreateBookmark

## <a name="properties"></a>Propiedades  
  
|||  
|-|-|  
|Id.|1020|  
|Palabras clave|WFRuntime|  
|Nivel|Verbose|  
|Canal|Microsoft-Windows-Application Server-Applications/Debug|  
  
## <a name="description"></a>Descripción  

 Indica que se ha creado un marcador para una actividad.  
  
## <a name="message"></a>Message  

 Se ha creado un marcador para la actividad ' %1 ', DisplayName: ' %2 ', InstanceId: ' %3 '.  BookmarkName: %4, BookmarkScope: %5.  
  
## <a name="details"></a>Detalles  
  
|Nombre del elemento de datos|Tipo del elemento de datos|Descripción|  
|--------------------|--------------------|-----------------|  
|Actividad|xs:string|El nombre de tipo de la actividad.|  
|DisplayName|xs:string|El nombre para mostrar de la actividad.|  
|InstanceId|xs:string|La identificación de instancia de la actividad.|  
|BookmarkName|xs:string|Nombre del marcador.|  
|BookmarkScope|xs:string|Ámbito del marcador.|  
|AppDomain|xs:string|La cadena devuelta por AppDomain.CurrentDomain.FriendlyName.|
