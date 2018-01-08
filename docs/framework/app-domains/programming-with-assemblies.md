---
title: Programar con ensamblados
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-bcl
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 46cc7d1be867ff94ca25d0d6ffaaf46a6dc9514b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="programming-with-assemblies"></a>Programar con ensamblados
Los ensamblados son los bloques de creación de .NET Framework; constituyen la unidad fundamental de implementación, control de versiones, reutilización, ámbitos de activación y permisos de seguridad. Los ensamblados proporcionan a Common Language Runtime la información necesaria para conocer las implementaciones de tipos. Son una colección de tipos y recursos compilados para funcionar en conjunto y formar una unidad lógica de funcionalidad. Para la ejecución, un tipo no existe fuera del contexto de un ensamblado.  
  
 En esta sección se describe cómo crear módulos, crear ensamblados a partir de módulos, crear un par de claves y firmar un ensamblado con un nombre seguro, e instalar un ensamblado en la caché global de ensamblados. Además, se explica cómo usar el [Desensamblador de MSIL (Ildasm.exe)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) para ver la información del manifiesto del ensamblado.  
  
> [!NOTE]
>  A partir de la versión 2.0 de .NET Framework, el tiempo de ejecución no cargará ningún ensamblado compilado con una versión de .NET Framework que tenga un número de versión superior al tiempo de ejecución cargado actualmente. Esto se aplica a la combinación de los componentes principal y secundario del número de versión.  
  
## <a name="in-this-section"></a>En esta sección  
 [Creación de ensamblados](../../../docs/framework/app-domains/create-assemblies.md)  
 Proporciona información general sobre los ensamblados de archivos individuales y múltiples archivos.  
  
 [Nombres de ensamblado](../../../docs/framework/app-domains/assembly-names.md)  
 Proporciona información general sobre la nomenclatura del ensamblado.  
  
 [Determinar el nombre completo de un ensamblado](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md)  
 Describe cómo determinar el nombre completo de un ensamblado.  
  
 [Ejecutar aplicaciones de Intranet con plena confianza](../../../docs/framework/app-domains/running-intranet-applications-in-full-trust.md)  
 Describe cómo especificar la directiva de seguridad heredada para los ensamblados de plena confianza en un recurso compartido de la intranet.  
  
 [Ubicación del ensamblado](../../../docs/framework/app-domains/assembly-location.md)  
 Proporciona una visión general de dónde ubicar los ensamblados.  
  
 [Compilar un ensamblado de un solo archivo](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)  
 Describe cómo crear un ensamblado de un solo archivo.  
  
 [Ensamblados de múltiples archivos](../../../docs/framework/app-domains/multifile-assemblies.md)  
 Describe las razones para crear ensamblados de varios archivos.  
  
 [Compilar un ensamblado de varios archivos](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 Describe cómo crear un ensamblado de varios archivos.  
  
 [Configurar atributos de ensamblados](../../../docs/framework/app-domains/set-assembly-attributes.md)  
 Describe los atributos de ensamblado y cómo establecerlos.  
  
 [Crear y utilizar ensamblados con nombre seguro](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 Describe cómo y por qué se firman los ensamblados con un nombre seguro e incluye temas de procedimientos.  
  
 [Retrasar la firma de un ensamblado](../../../docs/framework/app-domains/delay-sign-assembly.md)  
 Describe cómo se retrasa la firma de un ensamblado.  
  
 [Trabajar con ensamblados y la memoria caché global de ensamblados](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 Explica cómo y por qué se agregan ensamblados a la caché global de ensamblados e incluye temas de procedimientos.  
  
 [Ver el contenido de un ensamblado](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 Describe cómo usar el Desensamblador de MSIL (Ildasm.exe) para ver el contenido del ensamblado.  
  
 [Reenvío de tipos en Common Language Runtime](../../../docs/framework/app-domains/type-forwarding-in-the-common-language-runtime.md)  
 Describe cómo usar el reenvío de tipos para pasar un tipo a un ensamblado diferente sin interrumpir las aplicaciones existentes.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Reflection.Assembly>  
 Clase de .NET Framework que representa un ensamblado.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Obtener información sobre tipos y miembros desde un ensamblado](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 Describe cómo obtener mediante programación el tipo y otra información de un ensamblado.  
  
 [Ensamblados en Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Proporciona información conceptual sobre los ensamblados Common Language Runtime.  
  
 [Versiones de los ensamblados](../../../docs/framework/app-domains/assembly-versioning.md)  
 Proporciona información general sobre el enlace de ensamblado y los atributos <xref:System.Reflection.AssemblyVersionAttribute> y <xref:System.Reflection.AssemblyInformationalVersionAttribute>.  
  
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 Describe la forma en que el tiempo de ejecución determina el ensamblado que se va a usar para llevar a cabo una solicitud de enlace.  
  
 [Reflexión](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Describe cómo usar la clase **Reflection** para obtener información sobre un ensamblado.
