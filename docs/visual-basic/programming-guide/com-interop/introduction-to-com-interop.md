---
title: Información general sobre la interoperabilidad COM (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- interop assemblies
- COM interop [Visual Basic], about COM interop
ms.assetid: 8bd62e68-383d-407f-998b-29aa0ce0fd67
ms.openlocfilehash: 5e31bfafdc321bb514ecdadd49b7e2c6adf53948
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/10/2018
ms.locfileid: "44262183"
---
# <a name="introduction-to-com-interop-visual-basic"></a>Información general sobre la interoperabilidad COM (Visual Basic)
El modelo de objetos componentes (COM) permite a un objeto exponer su funcionalidad a otros componentes y aplicaciones host. Aunque los objetos COM han sido fundamentales para Windows durante muchos años de programación, las aplicaciones diseñadas para common language runtime (CLR) proporcionan muchas ventajas.  
  
 [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] aplicaciones reemplazará finalmente a aquellas que se desarrollaron con COM. Hasta entonces, es posible que deba usar o crear objetos COM con Visual Studio. Interoperabilidad con COM, o *interoperabilidad COM*, le permite utilizar objetos COM existentes mientras realiza la transición a la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] a su propio ritmo.  
  
 Mediante el uso de la [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] para crear componentes COM, puede usar la interoperabilidad COM sin registro. Esto le permite controlar qué versión de DLL se habilita cuando se instala en un equipo más de una versión y permite a los usuarios finales utilizar XCOPY o FTP para copiar la aplicación en un directorio adecuado en su equipo donde se puede ejecutar. Para obtener más información, consulte [interoperabilidad COM sin registro](../../../framework/interop/registration-free-com-interop.md).  
  
## <a name="managed-code-and-data"></a>Código administrado y datos  
 Código desarrollado para el [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] se conoce como *código administrado*y contiene metadatos que se utilizan por CLR. Datos usados por [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] aplicaciones se denomina *datos administrados* porque el tiempo de ejecución administra las tareas relacionadas con los datos, como la asignación y reclamar la memoria y realizar la comprobación de tipos. De forma predeterminada, Visual Basic .NET se usa código administrado y los datos, pero puede tener acceso a código no administrado y los datos de objetos COM mediante ensamblados de interoperabilidad (descritos más adelante en esta página).  
  
## <a name="assemblies"></a>Ensamblados  
 Un ensamblado es el principal bloque de creación de un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] aplicación. Es una colección de funciones que se ha creado, con control de versiones e implementada como una sola unidad de implementación que contiene uno o varios archivos. Cada ensamblado contiene un manifiesto del ensamblado.  
  
## <a name="type-libraries-and-assembly-manifests"></a>Bibliotecas de tipos y manifiestos de ensamblado  
 Bibliotecas de tipos describen las características de objetos COM, como los nombres de miembros y tipos de datos. Manifiestos de ensamblado realizan la misma función para [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] aplicaciones. Incluyen información acerca de lo siguiente:  
  
-   Identidad del ensamblado, versión, referencia cultural y firma digital.  
  
-   Archivos que componen la implementación del ensamblado.  
  
-   Tipos y recursos que componen el ensamblado. Esto incluye aquellas que se exportan desde él.  
  
-   Dependencias de tiempo de compilación en otros ensamblados.  
  
-   Permisos necesarios para que el ensamblado se ejecute correctamente.  
  
 Para obtener más información sobre los ensamblados y manifiestos de ensamblado, vea [ensamblados y caché Global de ensamblados](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md).  
  
### <a name="importing-and-exporting-type-libraries"></a>Importación y exportación de bibliotecas de tipos  
 Visual Studio contiene una utilidad, Tlbimp, que le permite importar información desde una biblioteca de tipos en un [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] aplicación. Puede generar las bibliotecas de tipos desde ensamblados mediante la utilidad Tlbexp.  
  
 Para obtener información sobre Tlbimp y Tlbexp, vea [Tlbimp.exe (importador de biblioteca)](../../../framework/tools/tlbimp-exe-type-library-importer.md) y [Tlbexp.exe (exportador de biblioteca)](../../../framework/tools/tlbexp-exe-type-library-exporter.md).  
  
## <a name="interop-assemblies"></a>Ensamblados de interoperabilidad  
 Ensamblados de interoperabilidad son [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ensamblados que puente entre administrado y código, los miembros de objeto de asignación COM equivalente [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] miembros administrados. Ensamblados de interoperabilidad creados por Visual Basic .NET controlan muchos de los detalles del trabajo con objetos COM, como el cálculo de referencias de interoperabilidad.  
  
## <a name="interoperability-marshaling"></a>El cálculo de referencias de interoperabilidad  
 Todos los [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] aplicaciones comparten un conjunto de tipos comunes que permiten la interoperabilidad de objetos, independientemente del lenguaje de programación que se usa. Los parámetros y valores devueltos de los objetos COM a veces, usan los tipos de datos que difieren de aquéllos utilizados en código administrado. *El cálculo de referencias de interoperabilidad* es el proceso de empaquetado de parámetros y valores devueltos en tipos de datos equivalentes enviados hacia y desde objetos COM. Para obtener más información, consulte [interoperativo](../../../framework/interop/interop-marshaling.md).  
  
## <a name="see-also"></a>Vea también

- [Interoperabilidad COM](../../../visual-basic/programming-guide/com-interop/index.md)  
- [Tutorial: Implementación de la herencia mediante objetos COM](../../../visual-basic/programming-guide/com-interop/walkthrough-implementing-inheritance-with-com-objects.md)  
- [Interoperating with Unmanaged Code](../../../framework/interop/index.md) (Interoperar con código no administrado)  
- [Solución de problemas de interoperabilidad](../../../visual-basic/programming-guide/com-interop/troubleshooting-interoperability.md)  
- [Ensamblados y Caché global de ensamblados](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
- [TlbImp.exe (Importador de la biblioteca de tipos)](../../../framework/tools/tlbimp-exe-type-library-importer.md)  
- [Tlbexp.exe (Exportador de la biblioteca de tipos)](../../../framework/tools/tlbexp-exe-type-library-exporter.md)  
- [Serialización de interoperabilidad](../../../framework/interop/interop-marshaling.md)  
- [Interoperabilidad COM sin registro](../../../framework/interop/registration-free-com-interop.md)
