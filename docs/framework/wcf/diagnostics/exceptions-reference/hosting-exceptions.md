---
title: Excepciones de hospedaje
ms.date: 03/30/2017
ms.assetid: ad9e14f8-fa17-4d59-b365-fe0e7ec17c98
ms.openlocfilehash: f2bc7d0ca09faa2598990437295d1abf0cff3c45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61934737"
---
# <a name="hosting-exceptions"></a>Excepciones de hospedaje
En este tema se detallan todas las excepciones generadas en el hospedaje.  
  
## <a name="exception-list"></a>Lista de excepciones  
  
|Código de recurso|Cadena de recurso|  
|-------------------|---------------------|  
|Hosting_AddressIsAbsoluteUri|No se permite el URI completo. Los URI completos no se permiten para la ServiceHostingEnvironment.EnsureServiceAvailable API. Utilice una ruta de acceso virtual para el servicio correspondiente.|  
|Hosting_BuildProviderCouldNotCreateType|El tipo CLR especificado no se puede cargar durante la compilación del servicio. Compruebe que este tipo está definida en un archivo de origen ubicado en la aplicación \\directorio \App_Code, contenido en un ensamblado compilado situado en la aplicación \\\bin directorio, o está presente en un ensamblado instalado en el Caché global de ensamblados. En el nombre de tipo se distingue entre mayúsculas y minúsculas. Los directorios como \\\App_Code y \\\bin debe estar ubicado en el directorio raíz de la aplicación. El \\\App_Code y \\\bin directorios no pueden estar anidados en subdirectorios.|
