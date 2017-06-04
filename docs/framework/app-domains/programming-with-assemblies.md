---
title: "Programar con ensamblados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ensamblados [.NET Framework], programar"
  - "programar ensamblados"
ms.assetid: 25918b15-701d-42c7-95fc-c290d08648d6
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Programar con ensamblados
Los ensamblados son los bloques de creación de .NET Framework; constituyen la unidad fundamental de implementación, control de versiones, reutilización, ámbito de activación y permisos de seguridad.  Los ensamblados proporcionan a Common Language Runtime la información necesaria para conocer las implementaciones de tipos.  Son colecciones de tipos y recursos compilados para funcionar conjuntamente y formar una unidad de funcionalidad lógica.  Para la ejecución, un tipo no existe fuera del contexto de un ensamblado.  
  
 En esta sección se describe cómo se crean módulos, ensamblados a partir de módulos y pares de claves, cómo se firma un ensamblado con un nombre seguro y cómo se instala un ensamblado en la caché global de ensamblados.  Además, se describe cómo se usa el [Desensamblador de MSIL \(Ildasm.exe\)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) para ver la información del manifiesto del ensamblado.  
  
> [!NOTE]
>  Si se inicia con la versión 2.0 de .NET Framework, el tiempo de ejecución no cargará un ensamblado compilado con una versión de .NET Framework posterior a la actualmente cargada en el tiempo de ejecución.  Esto se aplica a la combinación de componentes principales y secundarios del número de versión.  
  
## En esta sección  
 [Crear ensamblados](../../../docs/framework/app-domains/create-assemblies.md)  
 Proporciona información general sobre ensamblados de un único archivo y de varios archivos.  
  
 [Nombres de ensamblado](../../../docs/framework/app-domains/assembly-names.md)  
 Proporciona información general sobre la nomenclatura de ensamblados.  
  
 [Cómo: Determinar el nombre completo de un ensamblado](../../../docs/framework/app-domains/how-to-determine-assembly-fully-qualified-name.md)  
 Describe cómo determinar el nombre completo de un ensamblado.  
  
 [Ejecutar aplicaciones de Intranet con plena confianza](../../../docs/framework/app-domains/running-intranet-applications-in-full-trust.md)  
 Describe cómo se especifica la directiva de seguridad heredada en ensamblados de plena confianza de un recurso compartido de la intranet.  
  
 [Ubicación del ensamblado](../../../docs/framework/app-domains/assembly-location.md)  
 Proporciona información general sobre la ubicación de ensamblados.  
  
 [Cómo: Compilar un ensamblado de un solo archivo](../../../docs/framework/app-domains/how-to-build-a-single-file-assembly.md)  
 Describe cómo se crea un ensamblado de un único archivo.  
  
 [Ensamblados de varios archivos](../../../docs/framework/app-domains/multifile-assemblies.md)  
 Describe las razones para crear ensamblados de varios archivos.  
  
 [Cómo: Compilar un ensamblado de varios archivos](../../../docs/framework/app-domains/how-to-build-a-multifile-assembly.md)  
 Describe cómo se crea un ensamblado de varios archivos.  
  
 [Configurar atributos de ensamblados](../../../docs/framework/app-domains/set-assembly-attributes.md)  
 Describe los atributos de ensamblado y cómo se establecen.  
  
 [Crear y utilizar ensamblados con nombre seguro](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
 Explica cómo y por qué se firman los ensamblados con nombres seguros, e incluye temas del tipo Cómo...  
  
 [Retrasar la firma de un ensamblado](../../../docs/framework/app-domains/delay-sign-assembly.md)  
 Describe cómo se retrasa la firma de un ensamblado.  
  
 [Trabajar con ensamblados y la memoria caché global de ensamblados](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)  
 Explica cómo y por qué se agregan ensamblados a la caché global de ensamblados, e incluye temas del tipo Cómo...  
  
 [Cómo: Ver el contenido de un ensamblado](../../../docs/framework/app-domains/how-to-view-assembly-contents.md)  
 Describe cómo se usa el Desensamblador de MSIL \(Ildasm.exe\) para ver el contenido de los ensamblados.  
  
 [Reenvío de tipos en Common Language Runtime](../../../docs/framework/app-domains/type-forwarding-in-the-common-language-runtime.md)  
 Describe cómo utilizar el reenvío de tipos para pasar un tipo a un ensamblado diferente sin interrumpir las aplicaciones existentes.  
  
## Referencia  
 <xref:System.Reflection.Assembly>  
 La clase de .NET Framework que representa un ensamblado.  
  
## Secciones relacionadas  
 [Cómo: Obtener información sobre tipos y miembros desde un ensamblado](../../../docs/framework/app-domains/how-to-obtain-type-and-member-information-from-an-assembly.md)  
 Describe cómo se obtiene información de tipo y otra información de un ensamblado mediante programación.  
  
 [Ensamblados en Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)  
 Proporciona una introducción general a los conceptos de ensamblado de Common Language Runtime.  
  
 [Versiones de los ensamblados](../../../docs/framework/app-domains/assembly-versioning.md)  
 Proporciona una descripción general de los enlaces de ensamblado y de los atributos <xref:System.Reflection.AssemblyVersionAttribute> y <xref:System.Reflection.AssemblyInformationalVersionAttribute>.  
  
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
 Describe cómo el motor en tiempo de ejecución determina qué ensamblado se debe usar para satisfacer una solicitud de enlace.  
  
 [Reflection](../../../docs/framework/reflection-and-codedom/reflection.md)  
 Describe cómo se usa la clase **Reflection** para obtener información sobre un ensamblado.