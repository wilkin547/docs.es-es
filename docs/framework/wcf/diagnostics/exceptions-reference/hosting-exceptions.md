---
title: "Excepciones de hospedaje | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ad9e14f8-fa17-4d59-b365-fe0e7ec17c98
caps.latest.revision: 5
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 5
---
# Excepciones de hospedaje
En este tema se detallan todas las excepciones generadas en el hospedaje.  
  
## Lista de excepción  
  
|Código de recurso|Cadena de recurso|  
|-----------------------|-----------------------|  
|Hosting\_AddressIsAbsoluteUri|No se permite el URI completo.Los URI completos no se permiten para la ServiceHostingEnvironment.EnsureServiceAvailable API.Utilice una ruta de acceso virtual para el servicio correspondiente.|  
|Hosting\_BuildProviderCouldNotCreateType|El tipo CLR especificado no se puede cargar durante la compilación del servicio.Compruebe que este tipo está definido en un archivo de origen situado en el directorio de la aplicación \\\\App\_Code, contenido en un ensamblado compilado situado en el directorio de la aplicación \\\\bin, o está presente en un ensamblado instalado en la caché global de ensamblados.En el nombre de tipo se distingue entre mayúsculas y minúsculas.Los directorios como \\\\App\_Code y \\\\bin se deben situar en el directorio raíz de la aplicación.Los directorios \\\\App\_Code y \\\\bin no pueden estar anidados en subdirectorios.|