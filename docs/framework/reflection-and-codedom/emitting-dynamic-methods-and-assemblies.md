---
title: Emitir métodos y ensamblados dinámicos
ms.date: 08/30/2017
helpviewer_keywords:
- reflection emit
- dynamic assemblies
- metadata, emit interfaces
- reflection emit, overview
- assemblies [.NET Framework], emitting dynamic assemblies
ms.openlocfilehash: fda5a20eb7798086ec10415889454b4a8beba5f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79180528"
---
# <a name="emitting-dynamic-methods-and-assemblies"></a>Emitir métodos y ensamblados dinámicos

En esta sección se describe un conjunto de tipos administrados del espacio de nombres <xref:System.Reflection.Emit> que permite a un compilador o una herramienta emitir metadatos y el Lenguaje Intermedio de Microsoft (MSIL) en tiempo de ejecución y, opcionalmente, generar un archivo portable ejecutable (PE) en el disco. Los motores de scripts y los compiladores son los principales usuarios de este espacio de nombres. En esta sección, la funcionalidad proporcionada por el espacio de nombres <xref:System.Reflection.Emit> se conoce como emisión de la reflexión.  
  
La emisión de la reflexión permite lo siguiente:  
  
- Definir métodos globales ligeros en tiempo de ejecución, usando la clase <xref:System.Reflection.Emit.DynamicMethod>, y ejecutarlos usando delegados.  
  
- Definir ensamblados en tiempo de ejecución y, después, ejecutarlos o guardarlos en el disco.  
  
- Definir ensamblados en tiempo de ejecución, ejecutarlos y, después, descargarlos y permitir la recolección de elementos no utilizados para reclamar sus recursos.  
  
- Definir módulos en nuevos ensamblados en tiempo de ejecución y, después, ejecutarlos o guardarlos en el disco.  
  
- Definir tipos en módulos en tiempo de ejecución, crear instancias de estos tipos y llamar a sus métodos.  
  
- Definir información simbólica para módulos definidos que puedan usar herramientas como depuradores y generadores de perfiles de código.  
  
Además de los tipos administrados del espacio de nombres <xref:System.Reflection.Emit>, hay interfaces de metadatos no administradas que se describen en la documentación de referencia [Interfaces de metadatos](../unmanaged-api/metadata/metadata-interfaces.md). La emisión de reflexión administrada proporciona una comprobación más estricta de los errores semánticos y un mayor nivel de abstracción de los metadatos que las interfaces de metadatos no administradas.  
  
Otro recurso útil para trabajar con metadatos y MSIL es la documentación de Common Language Infrastructure (CLI), especialmente la sección II sobre la definición y la semántica de los metadatos y la partición III sobre el conjunto de instrucciones de CIL. La documentación está disponible en línea en el sitio web de [Ecma.](https://www.ecma-international.org/publications/standards/Ecma-335.htm)  
  
## <a name="in-this-section"></a>En esta sección
  
[Los problemas de seguridad en la reflexión emiten](security-issues-in-reflection-emit.md)  
Describe los problemas de seguridad relacionados con la creación de ensamblados dinámicos mediante emisión de la reflexión.  

[Cómo: Definir y ejecutar métodos dinámicos](how-to-define-and-execute-dynamic-methods.md) Muestra cómo ejecutar un método dinámico simple y un método dinámico enlazado a una instancia de una clase.

[Cómo: Definir un tipo genérico con emisión](how-to-define-a-generic-type-with-reflection-emit.md) de reflexión Muestra cómo crear un tipo genérico simple con dos parámetros de tipo, cómo aplicar restricciones de clase, interfaz y especiales a los parámetros de tipo y cómo crear miembros que usan los parámetros de tipo de la clase como tipos de parámetro y tipos de valor devuelto.

[Cómo: Definir un método genérico con emisión](how-to-define-a-generic-method-with-reflection-emit.md) de reflexión Muestra cómo crear, emitir e invocar un método genérico simple.

[Ensamblajes coleccionables para la generación](collectible-assemblies.md) de tipos dinámicos Presenta ensamblados coleccionables, que son ensamblados dinámicos que se pueden descargar sin descargar el dominio de aplicación en el que se crearon.
  
## <a name="reference"></a>Referencia  

<xref:System.Reflection.Emit.OpCodes>  
Cataloga los códigos de instrucción de MSIL que puede usar para compilar cuerpos de método.  
  
<xref:System.Reflection.Emit>  
Contiene clases administradas usadas para emitir ensamblados, tipos y métodos dinámicos.  
  
<xref:System.Type>  
Describe la clase <xref:System.Type>, que representa los tipos en reflexión administrada y emisión de la reflexión, y que es clave para el uso de estas tecnologías.  
  
<xref:System.Reflection>  
Contiene clases administradas usadas para explorar metadatos y código administrado.  
  
## <a name="related-sections"></a>Secciones relacionadas  

[Reflexión](reflection.md)  
Explica cómo explorar metadatos y código administrado.  
  
[Ensamblados de .NET](../../standard/assembly/index.md)  
Proporciona información general sobre los ensamblados de las implementaciones de. NET.
