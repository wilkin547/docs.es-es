---
title: Programación con ensamblados
ms.date: 08/20/2019
helpviewer_keywords:
- assemblies [.NET Framework], programming
- programming assemblies
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 03babe701b46eab54a76094c4728af80e6d9911e
ms.sourcegitcommit: 7b1ce327e8c84f115f007be4728d29a89efe11ef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2019
ms.locfileid: "70972622"
---
# <a name="program-with-assemblies"></a>Programación con ensamblados
Los ensamblados son los bloques de creación de .NET Framework; constituyen la unidad fundamental de implementación, control de versiones, reutilización, ámbitos de activación y permisos de seguridad. Los ensamblados proporcionan a Common Language Runtime la información necesaria para conocer las implementaciones de tipos. Son una colección de tipos y recursos compilados para funcionar en conjunto y formar una unidad lógica de funcionalidad. Para la ejecución, un tipo no existe fuera del contexto de un ensamblado.  
  
 En esta sección se describe cómo crear módulos, crear ensamblados a partir de módulos, crear un par de claves y firmar un ensamblado con un nombre seguro, e instalar un ensamblado en la caché global de ensamblados. Además, se explica cómo usar el [Desensamblador de MSIL (Ildasm.exe)](../../framework/tools/ildasm-exe-il-disassembler.md) para ver la información del manifiesto del ensamblado.  
  
> [!NOTE]
> A partir de la versión 2.0 de .NET Framework, el tiempo de ejecución no cargará ningún ensamblado compilado con una versión de .NET Framework que tenga un número de versión superior al tiempo de ejecución cargado actualmente. Esto se aplica a la combinación de los componentes principal y secundario del número de versión.  
  
## <a name="in-this-section"></a>En esta sección  
 [Creación de ensamblados](create.md)  
 Proporciona información general sobre los ensamblados de archivos individuales y múltiples archivos.  
  
 [Nombres de ensamblado](names.md)  
 Proporciona información general sobre la nomenclatura del ensamblado.  
  
 [Cómo: Determinar el nombre completo de un ensamblado](find-fully-qualified-name.md)  
 Describe cómo determinar el nombre completo de un ensamblado.  
  
 [Ejecutar aplicaciones de Intranet con plena confianza](../../framework/app-domains/running-intranet-applications-in-full-trust.md)  
 Describe cómo especificar la directiva de seguridad heredada para los ensamblados de plena confianza en un recurso compartido de la intranet.  
  
 [Ubicación del ensamblado](location.md)  
 Proporciona una visión general de dónde ubicar los ensamblados.  
  
 [Cómo: Compilar un ensamblado de un solo archivo](../../framework/app-domains/build-single-file-assembly.md)  
 Describe cómo crear un ensamblado de un solo archivo.  
  
 [Ensamblados de varios archivos](../../framework/app-domains/multifile-assemblies.md)  
 Describe las razones para crear ensamblados de varios archivos.  
  
 [Cómo: Compilar un ensamblado de varios archivos](../../framework/app-domains/build-multifile-assembly.md)  
 Describe cómo crear un ensamblado de varios archivos.  
  
 [Establecer atributos de ensamblado](set-attributes.md)  
 Describe los atributos de ensamblado y cómo establecerlos.  
  
 [Creación y uso de ensamblados con nombre seguro](create-use-strong-named.md)  
 Describe cómo y por qué se firman los ensamblados con un nombre seguro e incluye temas de procedimientos.  
  
 [Retraso de la firma de un ensamblado](delay-sign.md)  
 Describe cómo se retrasa la firma de un ensamblado.  
  
 [Trabajar con ensamblados y la memoria caché global de ensamblados](../../framework/app-domains/working-with-assemblies-and-the-gac.md)  
 Explica cómo y por qué se agregan ensamblados a la caché global de ensamblados e incluye temas de procedimientos.  
  
 [Cómo: Ver el contenido de un ensamblado](view-contents.md)  
 Describe cómo usar el Desensamblador de MSIL (Ildasm.exe) para ver el contenido del ensamblado.  
  
 [Reenvío de tipos en Common Language Runtime](type-forwarding.md)  
 Describe cómo usar el reenvío de tipos para pasar un tipo a un ensamblado diferente sin interrumpir las aplicaciones existentes.  
  
## <a name="reference"></a>Referencia  
 <xref:System.Reflection.Assembly>  
 Clase de .NET Framework que representa un ensamblado.  
  
## <a name="related-sections"></a>Secciones relacionadas  
 [Cómo: Obtener información sobre tipos y miembros desde un ensamblado](../../framework/reflection-and-codedom/get-type-member-information.md)  
 Describe cómo obtener mediante programación el tipo y otra información de un ensamblado.  
  
 [Ensamblados de .NET](index.md)  
 Proporciona información conceptual sobre los ensamblados Common Language Runtime.  
  
 [Versiones de los ensamblados](versioning.md)  
 Proporciona información general sobre el enlace de ensamblado y los atributos <xref:System.Reflection.AssemblyVersionAttribute> y <xref:System.Reflection.AssemblyInformationalVersionAttribute>.  
  
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../framework/deployment/how-the-runtime-locates-assemblies.md)  
 Describe la forma en que el tiempo de ejecución determina el ensamblado que se va a usar para llevar a cabo una solicitud de enlace.  
  
 [Reflexión](../../framework/reflection-and-codedom/reflection.md)   
 Describe cómo usar la clase **Reflection** para obtener información sobre un ensamblado.
