---
title: Excepciones de hospedaje
ms.date: 03/30/2017
ms.assetid: ad9e14f8-fa17-4d59-b365-fe0e7ec17c98
ms.openlocfilehash: f2bc7d0ca09faa2598990437295d1abf0cff3c45
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="hosting-exceptions"></a>Excepciones de hospedaje
En este tema se detallan todas las excepciones generadas en el hospedaje.  
  
## <a name="exception-list"></a>Lista de excepciones  
  
|Código de recurso|Cadena de recurso|  
|-------------------|---------------------|  
|Hosting_AddressIsAbsoluteUri|No se permite el URI completo. Los URI completos no se permiten para la ServiceHostingEnvironment.EnsureServiceAvailable API. Utilice una ruta de acceso virtual para el servicio correspondiente.|  
|Hosting_BuildProviderCouldNotCreateType|El tipo CLR especificado no se puede cargar durante la compilación del servicio. Compruebe que este tipo está definido en un archivo de origen que se encuentra en la aplicación \\directorio \App_Code, contenido en un ensamblado compilado situado en la aplicación \\\bin directorio o está presente en un ensamblado instalado en la Caché global de ensamblados. En el nombre de tipo se distingue entre mayúsculas y minúsculas. Los directorios como \\\App_Code y \\\bin debe estar ubicado en el directorio raíz de la aplicación. El \\\App_Code y \\\bin directorios no pueden estar anidados en subdirectorios.|
