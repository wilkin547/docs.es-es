---
title: Ensamblados en Common Language Runtime
ms.date: 03/30/2017
helpviewer_keywords:
- dynamic assemblies
- security [.NET Framework], boundaries
- boundaries of assemblies
- assemblies [.NET Framework], about
- assemblies [.NET Framework], boundaries
- reference scope boundaries
- assemblies [.NET Framework]
- version boundaries
- type boundaries
ms.assetid: 2cfebe19-7436-49f1-bd99-3c4019f0b676
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b27a8d89b0345082b8cf06c3eb141e73e2bf0faf
ms.sourcegitcommit: 29a9b29d8b7d07b9c59d46628da754a8bff57fa4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/17/2019
ms.locfileid: "69567363"
---
# <a name="assemblies-in-the-common-language-runtime"></a>Ensamblados en Common Language Runtime
Los ensamblados son los bloques de creación de las aplicaciones .NET Framework; constituyen la unidad fundamental de implementación, control de versiones, reutilización, ámbitos de activación y permisos de seguridad. Un ensamblado es una colección de tipos y recursos compilados para funcionar en conjunto y formar una unidad lógica de funcionalidad. Los ensamblados proporcionan a Common Language Runtime la información necesaria para conocer las implementaciones de tipos. Para la ejecución, un tipo no existe fuera del contexto de un ensamblado.  
  
 Un ensamblado realiza las funciones siguientes:  
  
- Contiene el código que ejecuta Common Language Runtime. El código del lenguaje intermedio de Microsoft (MSIL) de un archivo ejecutable portable (PE) no se ejecuta si no tiene asociado un manifiesto del ensamblado. Hay que tener en cuenta que cada ensamblado solo puede tener un punto de entrada (es decir, `DllMain`, `WinMain` o `Main`).  
  
- Crea un límite de seguridad. Un ensamblado es la unidad en la que se solicitan y conceden los permisos. Para más información sobre los límites de seguridad en lo que respecta a los ensamblados, vea [Consideraciones de seguridad sobre ensamblados](../../../docs/framework/app-domains/assembly-security-considerations.md).  
  
- Crea un límite de tipos. La identidad de cada tipo incluye el nombre del ensamblado en que reside. Por ello, un tipo `MyType` cargado en el ámbito de un ensamblado no es igual que un tipo denominado `MyType` cargado en el ámbito de otro ensamblado.  
  
- Crea un límite de ámbito de referencia. El manifiesto del ensamblado contiene los metadatos del ensamblado que se utilizan para resolver tipos y satisfacer las solicitudes de recursos. Especifica los tipos y recursos que se exponen fuera del ensamblado. El manifiesto también enumera otros ensamblados de los que depende.  
  
- Forma un límite de versión. El ensamblado es la unidad versionable más pequeña de Common Language Runtime; todos los tipos y recursos del mismo ensamblado pertenecen a la misma versión. El manifiesto del ensamblado describe las dependencias de versión que se especifiquen para los ensamblados dependientes. Para más información sobre las versiones, vea [Versiones de los ensamblados](../../../docs/framework/app-domains/assembly-versioning.md).  
  
- Crea una unidad de implementación. Cuando se inicia una aplicación, sólo deben estar presentes los ensamblados a los que llama la aplicación inicialmente. Los demás ensamblados, como los recursos de localización o los ensamblados que contengan clases de utilidad, se pueden recuperar a petición. De este modo, se puede mantener la simplicidad y transparencia de las aplicaciones la primera vez que se descargan. Para más información sobre cómo implementar ensamblados, vea [Implementar .NET Framework y aplicaciones](../../../docs/framework/deployment/index.md).  
  
- Es la unidad que permite la ejecución en paralelo. Para más información sobre cómo ejecutar varias versiones de un ensamblado, vea [Ensamblados y ejecución simultánea](../../../docs/framework/app-domains/assemblies-and-side-by-side-execution.md).  
  
 Los ensamblados pueden ser estáticos o dinámicos. Los ensamblados estáticos pueden incluir tipos de .NET Framework (interfaces y clases), así como recursos para el ensamblado (mapas de bits, archivos JPEG, archivos de recursos, etc.). Los ensamblados estáticos se almacenan en el disco, en archivos ejecutables portables PE. También se puede utilizar .NET Framework para crear ensamblados dinámicos, que se ejecutan directamente desde la memoria y no se guardan en el disco antes de su ejecución. Los ensamblados dinámicos se pueden guardar en el disco una vez que se hayan ejecutado.  
  
 Existen varias formas de crear ensamblados. Puede usar herramientas de desarrollo, como Visual Studio, que haya empleado anteriormente para crear archivos .dll o .exe. Puede utilizar las herramientas suministradas en Windows SDK para generar ensamblados con módulos creados en otros entornos de programación. También puede utilizar las API de Common Language Runtime, como <xref:System.Reflection.Emit?displayProperty=nameWithType>, para crear ensamblados dinámicos.  
  
## <a name="related-topics"></a>Temas relacionados  
  
|Title|DESCRIPCIÓN|  
|-----------|-----------------|  
|[Contenido de los ensamblados](../../../docs/framework/app-domains/assembly-contents.md)|Describe los elementos que componen el ensamblado.|  
|[Manifiesto del ensamblado](../../../docs/framework/app-domains/assembly-manifest.md)|Describe los datos incluidos en el manifiesto del ensamblado y cómo se almacenan en los ensamblados.|  
|[Caché global de ensamblados](../../../docs/framework/app-domains/gac.md)|Describe la memoria caché global de ensamblados y cómo se utiliza con los ensamblados.|  
|[Ensamblados con nombre seguro](../../../docs/framework/app-domains/strong-named-assemblies.md)|Describe las características de los ensamblados con nombre seguro.|  
|[Consideraciones de seguridad sobre ensamblados](../../../docs/framework/app-domains/assembly-security-considerations.md)|Explica cómo funciona la seguridad de los ensamblados.|  
|[Versiones de los ensamblados](../../../docs/framework/app-domains/assembly-versioning.md)|Ofrece información general sobre la directiva de versiones de .NET Framework.|  
|[Colocación de ensamblados](../../../docs/framework/app-domains/assembly-placement.md)|Explica dónde ubicar los ensamblados.|  
|[Ensamblados y ejecución simultánea](../../../docs/framework/app-domains/assemblies-and-side-by-side-execution.md)|Proporciona información general sobre la utilización de varias versiones del motor en tiempo de ejecución o de un ensamblado simultáneamente.|  
|[Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)|Describe cómo crear, firmar y establecer atributos en los ensamblados.|  
|[Emitir métodos y ensamblados dinámicos](../../../docs/framework/reflection-and-codedom/emitting-dynamic-methods-and-assemblies.md)|Describe la creación de ensamblados dinámicos.|  
|[Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)|Describe cómo resuelve .NET Framework las referencias de ensamblado en tiempo de ejecución.|  
  
## <a name="reference"></a>Referencia  
 <xref:System.Reflection.Assembly?displayProperty=nameWithType>
