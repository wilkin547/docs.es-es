---
title: "Información general de la biblioteca de clases de .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- classes [.NET Framework], library overview
- class objects value type
- naming conventions [.NET Framework]
- types, .NET Framework
- user-defined types
- Visual Basic, data types
- data types [.NET Framework], C++
- Visual C#, data types
- libraries, .NET Framework class library
- data types [.NET Framework], JScript
- System namespace
- JScript, data types
- .NET Framework, class library
- type system [.NET Framework]
- data types [.NET Framework]
- value types
- data types [.NET Framework], Visual Basic
- Common Language Specification
- namespaces [.NET Framework]
- floating point value type
- class library [.NET Framework]
- CLS
- logical value type
- .NET Framework class library, about
- built-in types
- namespaces [.NET Framework], about namespaces
- Visual C++, data types
- members [.NET Framework], type
- data types [.NET Framework], C#
- integer value type
- base types, class library
ms.assetid: 7e4c5921-955d-4b06-8709-101873acf157
caps.latest.revision: 19
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b88c85eaeabc7fa87b483c7302bd5e135e3fd276
ms.contentlocale: es-es
ms.lasthandoff: 08/21/2017

---
# <a name="net-framework-class-library-overview"></a>Información general de la biblioteca de clases de .NET Framework
[!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] incluye clases, interfaces y tipos de valor que agilizan y optimizan el proceso de desarrollo y proporcionan acceso a las funciones del sistema. Para facilitar la interoperabilidad entre lenguajes, la mayoría de los tipos de .NET Framework son conformes a CLS y, por tanto, se pueden utilizar en todos los lenguajes de programación cuyo compilador satisfaga los requisitos de CLS.  
  
 Los tipos de .NET Framework son la base sobre la que se compilan aplicaciones, componentes y controles de .NET. [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] incluye tipos que realizan las funciones siguientes:  
  
-   Representar tipos de datos base y excepciones.  
  
-   Encapsular estructuras de datos.  
  
-   Realizar E/S.  
  
-   Obtener acceso a información sobre tipos cargados.  
  
-   Invocar las comprobaciones de seguridad de .NET Framework.  
  
-   Proporcionar: acceso a datos, interfaz gráfica para el usuario (GUI) independiente de cliente e interfaz GUI de cliente controlada por el servidor.  
  
 [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] proporciona un conjunto completo de interfaces, así como clases abstractas y concretas (no abstractas). Se pueden utilizar las clases concretas tal como están o, en muchos casos, derivar las clases propias de ellas. Para utilizar la funcionalidad de una interfaz se puede crear una clase que implemente la interfaz o derivar una clase de una de las clases de .NET Framework que implementa la interfaz.  
  
## <a name="naming-conventions"></a>Convenciones de nomenclatura  
 Los tipos de .NET Framework utilizan un esquema de nomenclatura con sintaxis de punto lo que indica la existencia de una jerarquía. Esta técnica agrupa tipos relacionados en espacios de nombres para que se pueda buscar y hacer referencia a ellos más fácilmente. La primera parte del nombre completo, hasta el punto situado más a la derecha, es el nombre del espacio de nombres. La última parte es el nombre de tipo. Por ejemplo, **System.Collections.ArrayList** representa el tipo **ArrayList** que pertenece al espacio de nombres **System.Collections**. Los tipos de **System.Collections** se pueden usar para manipular colecciones de objetos.  
  
 Este esquema de nomenclatura facilita a los programadores de bibliotecas la tarea de extender [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)] para poder crear grupos jerárquicos de tipos y asignarles nombre de forma coherente e ilustrativa. También permite identificar de forma inequívoca los tipos mediante su nombre completo (es decir, por su espacio de nombres y nombre de tipo), lo que evita que se produzcan conflictos entre los nombres de tipo. Se espera que los programadores de bibliotecas usen la siguiente convención cuando creen nombres para sus propios espacios de nombres:  
  
 *NombreCompañía*.*NombreTecnología*  
  
 Por ejemplo, el espacio de nombres Microsoft.Word cumple esta directriz.  
  
 El uso de modelos de nomenclatura para agrupar tipos relacionados en espacios de nombres es una forma muy útil de compilar y documentar bibliotecas de clases. Sin embargo, este esquema de nomenclatura no influye en la visibilidad, el acceso a miembros, la herencia, la seguridad o el enlace. Se puede hacer la partición de un espacio de nombres en varios ensamblados y un ensamblado individual puede contener tipos de varios espacios de nombres. El ensamblado proporciona la estructura formal para el control de versiones, la implementación, la seguridad, la carga y la visibilidad en Common Language Runtime.  
  
 Para obtener más información sobre espacios de nombres y nombres de tipos, vea [Common Type System](../../docs/standard/base-types/common-type-system.md).  
  
## <a name="system-namespace"></a>System (Espacio de nombres)  
 El espacio de nombres <xref:System> es el espacio de nombres de la raíz de los tipos fundamentales de [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)]. Este espacio de nombres contiene clases que representan los tipos de datos base que se utilizan en todas las aplicaciones: <xref:System.Object> (raíz de la jerarquía de herencia), <xref:System.Byte>, <xref:System.Char>, <xref:System.Array>, <xref:System.Int32>, <xref:System.String>, etc. Muchos de estos tipos se corresponden con los tipos de datos primitivos que utiliza el lenguaje de programación. Cuando se escribe código utilizando tipos de .NET Framework se puede utilizar la palabra clave correspondiente del lenguaje cuando se espera un tipo de datos base de .NET Framework.  
  
 En la tabla siguiente se muestra una lista de los tipos base que proporciona [!INCLUDE[dnprdnshort](../../includes/dnprdnshort-md.md)], se describe brevemente cada tipo y se indica el tipo correspondiente de Visual Basic, C#, C++ y JScript.  
  
|Categoría|Nombre de la clase|Descripción|Tipo de datos en Visual Basic|Tipo de datos en C#|Tipo de datos de C++|Tipo de datos en JScript|  
|--------------|----------------|-----------------|----------------------------|-------------------|---------------------|-----------------------|  
|Integer|<xref:System.Byte>|Entero de 8 bits sin signo.|**Byte**|**byte**|**unsigned char**|**Byte**|  
||<xref:System.SByte>|Entero de 8 bits con signo.<br /><br /> No es conforme a CLS.|**SByte**|**sbyte**|**char**<br /><br /> O bien<br /><br /> **signed** **char**|**SByte**|  
||<xref:System.Int16>|Entero de 16 bits con signo.|**Short**|**short**|**short**|**short**|  
||<xref:System.Int32>|Entero de 32 bits con signo.|**Integer**|**int**|**int**<br /><br /> O bien<br /><br /> **long**|**int**|  
||<xref:System.Int64>|Entero de 64 bits con signo.|**Long**|**long**|**__int64**|**long**|  
||<xref:System.UInt16>|Entero de 16 bits sin signo.<br /><br /> No es conforme a CLS.|**UShort**|**ushort**|**unsigned short**|**UInt16**|  
||<xref:System.UInt32>|Entero de 32 bits sin signo.<br /><br /> No es conforme a CLS.|**UInteger**|**uint**|**unsigned int**<br /><br /> O bien<br /><br /> **unsigned long**|**UInt32**|  
||<xref:System.UInt64>|Entero de 64 bits sin signo.<br /><br /> No es conforme a CLS.|**ULong**|**ulong**|**unsigned __int64**|**UInt64**|  
|Punto flotante|<xref:System.Single>|Número de punto flotante (32 bits) de precisión sencilla.|**Single**|**float**|**float**|**float**|  
||<xref:System.Double>|Número de punto flotante (64 bits) de doble precisión.|**Double**|**double**|**double**|**double**|  
|Lógico|<xref:System.Boolean>|Valor booleano (verdadero o falso).|**Boolean**|**bool**|**bool**|**bool**|  
|Otros|<xref:System.Char>|Carácter Unicode (16 bits).|**Char**|**char**|**wchar_t**|**char**|  
||<xref:System.Decimal>|Valor decimal (128 bits).|**Decimal**|**decimal**|**Decimal**|**Decimal**|  
||<xref:System.IntPtr>|Entero con signo cuyo tamaño depende de la plataforma subyacente (valor de 32 bits en una plataforma de 32 bits y valor de 64 bits en una plataforma de 64 bits).|**IntPtr**<br /><br /> No dispone de un tipo integrado.|**IntPtr**<br /><br /> No dispone de un tipo integrado.|**IntPtr**<br /><br /> No dispone de un tipo integrado.|**IntPtr**|  
||<xref:System.UIntPtr>|Entero sin signo cuyo tamaño depende de la plataforma subyacente (valor de 32 bits en una plataforma de 32 bits y valor de 64 bits en una plataforma de 64 bits).<br /><br /> No es conforme a CLS.|**UIntPtr**<br /><br /> No dispone de un tipo integrado.|**UIntPtr**<br /><br /> No dispone de un tipo integrado.|**UIntPtr**<br /><br /> No dispone de un tipo integrado.|**UIntPtr**|  
Objetos de clase|<xref:System.Object>|Base de la jerarquía de objetos.|**Objeto**|**object**|**Object\***|**Objeto**|  
||<xref:System.String>|Cadena inmutable de longitud fija de caracteres Unicode.|**String**|**string**|**String\***|**String**|  
  
 Además de los tipos de datos base, el espacio de nombres <xref:System> contiene más de 100 clases, que comprenden desde las clases que controlan excepciones hasta las clases que tratan conceptos básicos en tiempo de ejecución, como los dominios de aplicación y el recolector de elementos no utilizados. El espacio de nombres <xref:System> también contiene muchos espacios de nombres de segundo nivel.  
  
 Para obtener más información sobre los espacios de nombres, vea [Biblioteca de clases de .NET Framework](http://go.microsoft.com/fwlink/?LinkID=227195). La documentación de referencia proporciona información general breve de cada espacio de nombres así como una descripción precisa de cada tipo y sus miembros.  
  
## <a name="see-also"></a>Vea también  
 [Common Type System](../../docs/standard/base-types/common-type-system.md)   
 [Biblioteca de clases .NET Framework](http://go.microsoft.com/fwlink/?LinkID=227195)   
 [Información general](../../docs/framework/get-started/overview.md)

