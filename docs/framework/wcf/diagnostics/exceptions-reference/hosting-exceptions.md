---
title: Excepciones de hospedaje
ms.date: 03/30/2017
ms.assetid: ad9e14f8-fa17-4d59-b365-fe0e7ec17c98
ms.openlocfilehash: 342420f10ed53e4f4786ed9506cfde5fbfcfc957
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96263339"
---
# <a name="hosting-exceptions"></a>Excepciones de hospedaje

En este tema se detallan todas las excepciones generadas en el hospedaje.  
  
## <a name="exception-list"></a>Lista de excepciones  
  
|Código de recurso|Cadena de recurso|  
|-------------------|---------------------|  
|Hosting_AddressIsAbsoluteUri|No se permite el URI completo. Los URI completos no se permiten para la ServiceHostingEnvironment.EnsureServiceAvailable API. Utilice una ruta de acceso virtual para el servicio correspondiente.|  
|Hosting_BuildProviderCouldNotCreateType|El tipo CLR especificado no se puede cargar durante la compilación del servicio. Compruebe que este tipo se define en un archivo de código fuente ubicado en el \\ directorio \ App_Code de la aplicación, contenido en un ensamblado compilado ubicado en el directorio \bin de la aplicación \\ o presente en un ensamblado instalado en la caché global de ensamblados. En el nombre de tipo se distingue entre mayúsculas y minúsculas. Los directorios como \\ \ App_Code y \\ \Bin deben encontrarse en el directorio raíz de la aplicación. Los \\ directorios \ App_Code y \\ \Bin no se pueden anidar en subdirectorios.|
