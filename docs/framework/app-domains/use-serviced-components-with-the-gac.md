---
title: Utilizar componentes con servicio junto con la memoria caché global de ensamblados
description: Use componentes con servicio (componentes COM+ de código administrado) con la caché global de ensamblados en .NET. Vea si los servicios CLR y COM+ pueden administrar componentes que no son de GAC.
ms.date: 03/30/2017
helpviewer_keywords:
- assemblies [.NET Framework], global assembly cache
- GAC (global assembly cache), serviced components
- serviced components, global assembly cache
- global assembly cache, serviced components
ms.assetid: 3423e5d9-234c-4571-8161-e35f6d130128
ms.openlocfilehash: 6b7371865b7b1cedda0ee03b2cc28c74b5c3da0b
ms.sourcegitcommit: 1c37a894c923bea021a3cc38ce7cba946357bbe1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2020
ms.locfileid: "85104473"
---
# <a name="using-serviced-components-with-the-global-assembly-cache"></a>Utilizar componentes con servicio junto con la memoria caché global de ensamblados
Los componentes con servicio (componentes COM+ de código administrado) deben colocarse en la caché global de ensamblados. En algunos escenarios, Common Language Runtime y los Servicios COM+ pueden controlar los componentes con servicio que no están en la caché global de ensamblados; en otros escenarios no pueden. Estos escenarios ilustran lo siguiente:  
  
- En el caso de los componentes con servicio en una aplicación de servidor COM+, el ensamblado que contiene los componentes debe estar en la caché global de ensamblados, ya que Dllhost.exe no se ejecuta en el mismo directorio que contiene los componentes con servicio.  
  
- Para los componentes con servicio en una aplicación de COM+ Library, Common Language Runtime y COM+ Services pueden resolver la referencia al ensamblado que contiene los componentes buscando en el directorio actual. En este caso, el ensamblado no tiene que estar en la caché global de ensamblados.  
  
- Para los componentes con servicio en una aplicación ASP.NET, la situación es distinta. Si coloca el ensamblado que contiene los componentes con servicio en el directorio bin de la base de la aplicación y utiliza el registro a petición, se copiará una instantánea del ensamblado en la caché de descarga porque ASP.NET aprovecha las funcionalidades de copia de Common Language Runtime.  
  
## <a name="see-also"></a>Vea también

- [Trabajar con ensamblados y la memoria caché global de ensamblados](working-with-assemblies-and-the-gac.md)
- [Gacutil.exe (Herramienta Caché global de ensamblados)](../tools/gacutil-exe-gac-tool.md)
