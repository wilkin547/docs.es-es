---
title: Introducción al lenguaje C# y .NET
description: Conozca los conceptos básicos de C# y .NET. Obtenga información general sobre el lenguaje C# y el ecosistema .NET.
ms.date: 10/13/2020
ms.openlocfilehash: 94d49be28fbdba8f58ca16e959a10643d6467c63
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160963"
---
# <a name="introduction-to-the-c-language-and-net"></a>Introducción al lenguaje C# y .NET

C# es un lenguaje orientado a objetos elegante y con seguridad de tipos que permite a los desarrolladores crear muchos tipos de aplicaciones seguras y sólidas que se ejecutan en el ecosistema de .NET.

## <a name="c-language"></a>lenguaje C#

La sintaxis de C# es muy expresiva, pero también sencilla y fácil de aprender. Cualquier persona familiarizada con C, C++, Java o JavaScript reconocerá al instante la sintaxis de llaves de C#. Los desarrolladores que conocen cualquiera de estos lenguajes podrán trabajar, normalmente, en C# de forma productiva en un espacio breve de tiempo. C# proporciona características eficaces como tipos que aceptan valores NULL, delegados, expresiones lambda, coincidencia de patrones y acceso directo a memoria seguro. C# admite métodos y tipos genéricos, que proporcionan una mayor seguridad de tipos, así como un mejor rendimiento. C# también proporciona iteradores, gracias a los que los implementadores de clases de colecciones pueden definir comportamientos personalizados para el código de cliente. Las expresiones de Language Integrated Query (LINQ) convierten la consulta fuertemente tipada en una construcción de lenguaje de primera clase.

En cuanto lenguaje orientado a objetos, C# admite los conceptos de encapsulación, herencia y polimorfismo. Una clase puede heredar directamente de una clase primaria, pero puede implementar cualquier número de interfaces. Los métodos que invalidan los métodos virtuales en una clase primaria requieren la palabra clave `override` como una manera de evitar redefiniciones accidentales. En C#, un struct es como una clase ligera; es un tipo asignado en la pila que puede implementar interfaces pero que no admite la herencia. C# también proporciona registros, que son tipos de clase cuyo propósito es, principalmente, almacenar valores de datos.

C# facilita el desarrollo de componentes de software mediante varias construcciones de lenguaje innovadoras, entre las que se incluyen las siguientes:

- Signaturas de método encapsulado llamadas *delegados*, que permiten notificaciones de eventos con seguridad de tipos.
- Propiedades, que actúan como descriptores de acceso para variables miembro privadas.
- Atributos, que proporcionan metadatos declarativos sobre tipos en tiempo de ejecución.
- Comentarios de doc.umentación XML insertados
- Language Integrated Query (LINQ), que proporciona funcionalidades de consulta integradas en diversos orígenes de datos.
- Coincidencia de patrones, que permite el flujo de control mediante la inspección de tipos de datos y valores.

Puede interactuar con los componentes nativos mediante un proceso denominado "interoperabilidad". La interoperabilidad permite que los programas de C# hagan casi todo lo que puede hacer una aplicación C++ nativa. C# admite incluso el uso de punteros y el concepto de código "no seguro" en los casos en los que el acceso directo a memoria es crítico.

El proceso de compilación de C# es simple en comparación con C y C++ y más flexible que en Java. No hay ningún archivo de encabezado independiente y ningún requisito de declaración de métodos y tipos en un orden en particular. Un archivo de código fuente de C# puede definir cualquier número de clases, structs, interfaces y eventos.

Los siguientes son recursos adicionales de C#:

- Para obtener una buena introducción general al lenguaje, consulte la página [Paseo por el lenguaje C#](../tour-of-csharp/index.md).
- Para más información sobre aspectos específicos del lenguaje C#, consulte la [referencia de C#](../language-reference/index.md).
- Para más información sobre LINQ, consulte [LINQ (Language-Integrated Query)](../programming-guide/concepts/linq/index.md).

## <a name="net-platform-architecture"></a>Arquitectura de la plataforma .NET

Los programas de C# se ejecutan en .NET, un sistema de ejecución virtual denominado Common Language Runtime (CLR) y un conjunto unificado de bibliotecas de clases. CLR es la implementación comercial de Microsoft del estándar internacional Common Language Infrastructure (CLI). CLI es la base para crear entornos de ejecución y desarrollo en los que los lenguajes y las bibliotecas funcionan juntos sin problemas.

El código fuente escrito en C# se compila en un [lenguaje intermedio (IL)](../../standard/managed-code.md) que guarda conformidad con la especificación de CLI. El código y los recursos de IL, como mapas de bits y cadenas, se almacenan en un ensamblado, normalmente con una extensión .dll. Un ensamblado contiene un manifiesto que proporciona información sobre los tipos, la versión y la referencia cultural.

Cuando se ejecuta el programa C#, el ensamblado se carga en CLR. CLR realiza la compilación Just-In-Time (JIT) para convertir el código IL en instrucciones de máquina nativas. Además, CLR proporciona otros servicios relacionados con la recolección de elementos no utilizados, el control de excepciones y la administración de recursos. El código que se ejecuta en el CLR se conoce a veces como "código administrado", a diferencia del "código no administrado" que se compila en lenguaje de máquina nativo destinado a un sistema específico.

La interoperabilidad entre lenguajes es una característica principal de .NET. El código IL generado por el compilador de C# se ajusta a la especificación de tipo común (CTS). El código IL generado desde C# puede interactuar con el código generado a partir de las versiones de .NET de F# , Visual Basic, C++ o cualquiera de los más de 20 lenguajes compatibles con CTS. Un solo ensamblado puede contener varios módulos escritos en diferentes lenguajes .NET y los tipos se pueden hacer referencia mutuamente igual que si estuvieran escritos en el mismo lenguaje.

Además de los servicios en tiempo de ejecución, .NET también incluye amplias bibliotecas, que admiten muchas cargas de trabajo diferentes. Se organizan en espacios de nombres que proporcionan una gran variedad de funciones útiles para todo, desde la entrada y salida de archivos, pasando por la manipulación de cadenas en el análisis de XML y marcos de aplicaciones web, hasta controles de Windows Forms. En una aplicación de C# típica se usa la biblioteca de clases de .NET de forma extensa para controlar tareas comunes de infraestructura.

Para obtener más información sobre .NET, vea [Introducción a .NET](../../core/introduction.md).
