---
title: Introducción a la interoperabilidad COM
ms.date: 07/20/2015
helpviewer_keywords:
- interop assemblies
- COM interop [Visual Basic], about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
ms.openlocfilehash: 6c7caf266514c43e40135b33d848a688546acf1c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2020
ms.locfileid: "84396784"
---
# <a name="introduction-to-com-interop-visual-basic"></a>Información general sobre la interoperabilidad COM (Visual Basic)
El modelo de objetos componentes (COM) permite a un objeto exponer su funcionalidad a otros componentes y a las aplicaciones host. Aunque los objetos COM son fundamentales para la programación de Windows durante muchos años, las aplicaciones diseñadas para el Common Language Runtime (CLR) ofrecen muchas ventajas.  
  
 .NET Framework aplicaciones reemplazarán finalmente a las que se desarrollaron con COM. Hasta entonces, puede que tenga que usar o crear objetos COM mediante Visual Studio. La interoperabilidad con COM, o la *interoperabilidad com*, le permite usar objetos com existentes mientras realiza la transición al .NET Framework a su propio ritmo.  
  
 Mediante el .NET Framework para crear componentes COM, puede usar la interoperabilidad COM sin registro. Esto le permite controlar qué versión de DLL está habilitada cuando se instala más de una versión en un equipo y permite a los usuarios finales usar XCOPY o FTP para copiar la aplicación en un directorio adecuado en su equipo donde se puede ejecutar. Para obtener más información, consulte [interoperabilidad com sin registro](../../../framework/interop/registration-free-com-interop.md).  
  
## <a name="managed-code-and-data"></a>Código administrado y datos  
 El código desarrollado para el .NET Framework se conoce como *código administrado*y contiene metadatos utilizados por el CLR. Los datos utilizados por .NET Framework aplicaciones se denominan *datos administrados* porque el tiempo de ejecución administra tareas relacionadas con datos, como la asignación y la recuperación de memoria y la comprobación de tipos. De forma predeterminada, Visual Basic .NET utiliza código y datos administrados, pero puede tener acceso al código no administrado y a los datos de objetos COM mediante ensamblados de interoperabilidad (que se describen más adelante en esta página).  
  
## <a name="assemblies"></a>Ensamblados  
 Un ensamblado es el bloque de creación principal de una aplicación .NET Framework. Se trata de una colección de funciones que se compila, se versionan e implementan como una sola unidad de implementación que contiene uno o varios archivos. Cada ensamblado contiene un manifiesto de ensamblado.  
  
## <a name="type-libraries-and-assembly-manifests"></a>Bibliotecas de tipos y manifiestos de ensamblado  
 Las bibliotecas de tipos describen las características de los objetos COM, como los nombres de los miembros y los tipos de datos. Los manifiestos de ensamblado realizan la misma función para .NET Framework aplicaciones. Incluyen información acerca de lo siguiente:  
  
- Identidad del ensamblado, versión, referencia cultural y firma digital.  
  
- Archivos que componen la implementación del ensamblado.  
  
- Tipos y recursos que componen el ensamblado. Esto incluye los que se exportan desde él.  
  
- Dependencias en tiempo de compilación de otros ensamblados.  
  
- Permisos necesarios para que el ensamblado se ejecute correctamente.  
  
 Para obtener más información sobre los ensamblados y los manifiestos de ensamblado, vea [ensamblados en .net](../../../standard/assembly/index.md).  
  
### <a name="importing-and-exporting-type-libraries"></a>Importar y exportar bibliotecas de tipos  
 Visual Studio contiene una utilidad, Tlbimp, que le permite importar información de una biblioteca de tipos en una aplicación .NET Framework. Puede generar bibliotecas de tipos a partir de ensamblados mediante la utilidad Tlbexp.  
  
 Para obtener información acerca de Tlbimp y Tlbexp, vea [Tlbimp. exe (importador de la biblioteca de tipos)](../../../framework/tools/tlbimp-exe-type-library-importer.md) y [Tlbexp. exe (exportador de la biblioteca de tipos)](../../../framework/tools/tlbexp-exe-type-library-exporter.md).  
  
## <a name="interop-assemblies"></a>Ensamblados de interoperabilidad  
 Los ensamblados de interoperabilidad son .NET Framework ensamblados que se enlazan entre código administrado y no administrado, asignando miembros de objetos COM a miembros administrados de .NET Framework equivalentes. Los ensamblados de interoperabilidad creados por Visual Basic .NET controlan muchos de los detalles del trabajo con objetos COM, como el cálculo de referencias de interoperabilidad.  
  
## <a name="interoperability-marshaling"></a>Serialización de interoperabilidad  
 Todas las aplicaciones .NET Framework comparten un conjunto de tipos comunes que permiten la interoperabilidad de objetos, independientemente del lenguaje de programación que se use. Los parámetros y los valores devueltos de los objetos COM a veces utilizan tipos de datos que difieren de los usados en código administrado. El *cálculo de referencias de interoperabilidad* es el proceso de empaquetar parámetros y devolver valores en tipos de datos equivalentes a medida que se mueven a objetos com y desde ellos. Para obtener más información, consulte [serialización de interoperabilidad](../../../framework/interop/interop-marshaling.md).  
  
## <a name="see-also"></a>Consulte también

- [Interoperabilidad COM](index.md)
- [Tutorial: Implementación de la herencia mediante objetos COM](walkthrough-implementing-inheritance-with-com-objects.md)
- [Interoperar con código no administrado](../../../framework/interop/index.md)
- [Solución de problemas de interoperabilidad](troubleshooting-interoperability.md)
- [Ensamblados de .NET](../../../standard/assembly/index.md)
- [TlbImp.exe (Importador de la biblioteca de tipos)](../../../framework/tools/tlbimp-exe-type-library-importer.md)
- [Tlbexp.exe (Exportador de la biblioteca de tipos)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)
- [Serialización de interoperabilidad](../../../framework/interop/interop-marshaling.md)
- [Interoperabilidad COM sin registro](../../../framework/interop/registration-free-com-interop.md)
