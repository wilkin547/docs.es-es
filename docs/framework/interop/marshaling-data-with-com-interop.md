---
title: "serialización de datos con la interoperabilidad COM"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- COM interop, data marshaling
- marshaling data, COM interop
ms.assetid: 0bcdd7bf-5026-43eb-b08b-f03f90db9df9
caps.latest.revision: 12
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7e798f41f7c770fb0db0abf4a07e53cbaa6ccb40
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# <a name="marshaling-data-with-com-interop"></a>serialización de datos con la interoperabilidad COM
La interoperabilidad COM proporciona compatibilidad para usar objetos COM desde código administrado y para exponer objetos administrados en COM. La compatibilidad con el cálculo de referencias de datos desde y hacia COM es exhaustiva y el comportamiento del cálculo de referencias casi siempre es correcto.  
  
 [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] incluye las siguientes herramientas de interoperabilidad COM:  
  
-   [Importador de la biblioteca de tipos (Tlbimp.exe)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md), que convierte una biblioteca de tipos COM en un ensamblado de interoperabilidad. Desde este ensamblado, el servicio de serialización de interoperabilidad genera contenedores que realizan el cálculo de referencias de datos entre la memoria administrada y la no administrada.  
  
-   [Exportador de la biblioteca de tipos (Tlbexp.exe)](../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), que crea una biblioteca de tipos COM a partir un ensamblado y genera un contenedor que realiza la serialización durante las llamadas a métodos.  
  
 En esta sección se describen los procesos para personalizar los contenedores de interoperabilidad si puede (o debe) suministrar información adicional sobre tipos al contador de referencias.  
  
## <a name="in-this-section"></a>En esta sección  
 [Tipos de datos COM](http://msdn.microsoft.com/en-us/f93ae35d-a416-4218-8700-c8218cc90061)  
 Proporciona los tipos de datos administrados y no administrados correspondientes.  
  
 [Personalización de contenedores CCW](http://msdn.microsoft.com/en-us/825177d3-4b2c-4723-82be-ce6ca2c34ace)  
 Describe cómo serializar tipos de datos explícitamente mediante el atributo **MarshalAsAttribute** en tiempo de diseño.  
  
 [Personalización de contenedores RCW](http://msdn.microsoft.com/en-us/4652beaf-77d0-4f37-9687-ca193288c0be)  
 Describe cómo ajustar el comportamiento de serialización de tipos en un ensamblado de interoperabilidad y cómo definir tipos COM manualmente.  
  
 [Cómo: Migrar código administrado DCOM a WCF](../../../docs/framework/interop/how-to-migrate-managed-code-dcom-to-wcf.md)  
 Describe cómo migrar código DCOM administrado a WCF para obtener la solución más segura.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Interoperabilidad COM avanzada](http://msdn.microsoft.com/en-us/3ada36e5-2390-4d70-b490-6ad8de92f2fb)  
 Proporciona vínculos a más información sobre la incorporación de componentes COM en una aplicación de .NET Framework.  
  
 [Resumen de la conversión de ensamblados en bibliotecas de tipos](http://msdn.microsoft.com/en-us/3a37eefb-a76c-4000-9080-7dbbf66a4896)  
 Describe el proceso de conversión de la exportación de ensamblado a biblioteca de tipos.  
  
 [Resumen de la conversión de bibliotecas de tipos en ensamblados](http://msdn.microsoft.com/en-us/bf3f90c5-4770-4ab8-895c-3ba1055cc958)  
 Describe el proceso de conversión de la importación de biblioteca de tipos a ensamblado.  
  
 [Interoperar mediante tipos genéricos](http://msdn.microsoft.com/en-us/26b88e03-085b-4b53-94ba-a5a9c709ce58)  
 Describe qué acciones se admiten al usar tipos genéricos para la interoperabilidad COM.

