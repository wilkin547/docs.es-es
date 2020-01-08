---
title: Herramientas de .NET Framework
ms.date: 03/30/2017
helpviewer_keywords:
- command line, .NET Framework tools
- .NET Framework, tools
- tools [.NET Framework]
- running .NET Framework tools
ms.assetid: a2ca532d-91f7-426a-9303-417c2ee1247c
ms.openlocfilehash: 4503e2cff18f4aa901d20c76cfe4076a7fed3600
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715769"
---
# <a name="net-framework-tools"></a>Herramientas de .NET Framework

Las herramientas de .NET Framework facilitan la creación, implementación y administración de aplicaciones y componentes dirigidos a .NET Framework.

La mayoría de las herramientas de .NET Framework que se describen en esta sección se instalan automáticamente con Visual Studio. Para descargar Visual Studio, visite la página [Descargas de Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).

Puede ejecutar todas las herramientas desde la línea de comandos excepto Visor de la memoria caché de ensamblados (*Shfusion.dll*). Debe obtener acceso a *Shfusion.dll* desde el Explorador de archivos.
  
Para ejecutar las herramientas de línea de comandos, se recomienda usar el Símbolo del sistema para desarrolladores de Visual Studio. Estas utilidades permiten ejecutar las herramientas fácilmente, sin navegar hasta la carpeta de instalación. Para más información, consulte [Símbolos del sistema](developer-command-prompt-for-vs.md).

> [!NOTE]
> Algunas herramientas son específicas de los equipos de 32 bits o de los equipos de 64 bits. Asegúrese de ejecutar la versión adecuada de la herramienta para su equipo.

## <a name="in-this-section"></a>En esta sección

- [Al.exe (Assembly Linker)](al-exe-assembly-linker.md)  
Genera un archivo que tiene un manifiesto del ensamblado de módulos o archivos de recursos.

- [Aximp.exe (Importador de controles ActiveX de Windows Forms)](aximp-exe-windows-forms-activex-control-importer.md)  
Convierte definiciones de tipos de una biblioteca de tipos COM para un control ActiveX en un control de Windows Forms.

- [Caspol.exe (Herramienta de la directiva de seguridad de acceso del código)](caspol-exe-code-access-security-policy-tool.md)  
Esta herramienta le permite ver y configurar la directiva de seguridad correspondiente a los niveles de directiva de equipo, de usuario y de empresa. En .NET Framework 4 y versiones posteriores, esta herramienta no afecta a la directiva de seguridad de acceso del código (CAS), a menos que el elemento [\<legacyCasPolicy>](../configure-apps/file-schema/runtime/netfx40-legacysecuritypolicy-element.md) esté establecido en `true`. Para más información, consulte [Cambios de seguridad](../security/security-changes.md).

- [Cert2spc.exe (Herramienta de prueba de certificados del publicador de software)](cert2spc-exe-software-publisher-certificate-test-tool.md)  
Crea un certificado de publicador de software (SPC) a partir de uno o varios certificados X.509. Esta herramienta sólo se utiliza para pruebas.

- [Certmgr.exe (Herramienta de administración de certificados)](certmgr-exe-certificate-manager-tool.md)  
Administra certificados, listas de certificados de confianza (certificate trust lists, CTL) y listas de revocaciones de certificados (certificate revocation lists, CRL).

- [Clrver.exe (herramienta de versión de CLR)](clrver-exe-clr-version-tool.md)  
Notifica todas las versiones instaladas de Common Language Runtime (CLR) en el equipo.

- [Símbolos del sistema](developer-command-prompt-for-vs.md)  
Le permite usar las herramientas de .NET Framework más fácilmente. Es un símbolo del sistema que establece automáticamente variables de entorno específicas.

- [CorFlags.exe (Herramienta de conversión de CorFlags)](corflags-exe-corflags-conversion-tool.md)  
Le permite configurar la sección CorFlags del encabezado de una imagen ejecutable portátil (PE).

- [Fuslogvw.exe (Visor de registro de enlaces de ensamblados)](fuslogvw-exe-assembly-binding-log-viewer.md)  
Muestra información sobre los enlaces de ensamblado para ayudarle a diagnosticar por qué .NET Framework no puede encontrar un ensamblado en tiempo de ejecución.

- [Gacutil.exe (Herramienta Caché global de ensamblados)](gacutil-exe-gac-tool.md)  
Le permite ver y manipular el contenido de la caché global de ensamblados y de la memoria caché de descarga.

- [Ilasm.exe (Ensamblador de IL)](ilasm-exe-il-assembler.md)  
Genera un archivo ejecutable portable (PE) a partir de lenguaje intermedio (IL). Se puede ejecutar el archivo ejecutable resultante para determinar si IL funciona de la manera esperada.

- [Ildasm.exe (Desensamblador de IL)](ildasm-exe-il-disassembler.md)  
Toma un archivo portable ejecutable (PE) que contiene código de lenguaje intermedio (IL) y crea un archivo de texto que se puede usar como entrada para el Ensamblador de IL (Ilasm.exe).

- [Installutil.exe (Herramienta Installer)](installutil-exe-installer-tool.md)  
Le permite instalar y desinstalar recursos de servidor mediante la ejecución de los componentes del instalador en un ensamblado especificado. (Funciona con las clases del espacio de nombres <xref:System.Configuration.Install>).

- [Lc.exe (Compilador de licencias)](lc-exe-license-compiler.md)  
Lee archivos de texto que contienen información sobre licencias y crea un archivo *.licenses* que se puede incrustar en un archivo ejecutable de Common Language Runtime como un recurso.

- [Mage.exe (Herramienta de generación y edición de manifiestos)](mage-exe-manifest-generation-and-editing-tool.md)  
Le permite crear, editar y firmar manifiestos de aplicación y de implementación. Como herramienta de línea de comandos, *Mage.exe* se puede ejecutar desde scripts por lotes y desde otras aplicaciones basadas en Windows, incluidas las aplicaciones de ASP.NET.

- [MageUI.exe (Herramienta de generación y edición de manifiestos, cliente gráfico)](mageui-exe-manifest-generation-and-editing-tool-graphical-client.md)  
Admite la misma funcionalidad que la herramienta de línea de comandos Mage.exe, pero usa una interfaz de usuario (IU) basada en Windows. Admite la misma funcionalidad que la herramienta de línea de comandos *Mage.exe*, pero usa una interfaz de usuario (IU) basada en Windows.

- [MDbg.exe (depurador de línea de comandos .NET Framework)](mdbg-exe.md)  
Ayuda a los proveedores de herramientas y desarrolladores de aplicaciones encontrar y corregir errores en los programas que tienen como destino Common Language Runtime de .NET Framework. Esta herramienta utiliza el runtime de la API de depuración para proporcionar servicios de depuración.

- [Mgmtclassgen.exe (Generador de clases fuertemente tipadas para administración)](mgmtclassgen-exe.md)  
Le permite generar una clase administrada enlazada en tiempo de compilación para una clase especificada de Instrumental de administración de Windows (WMI).

- [Mpgo.exe (Herramienta de optimización guiada por perfiles administrados)](mpgo-exe-managed-profile-guided-optimization-tool.md)  
Permite adaptar ensamblados de imagen nativa mediante escenarios de usuario final comunes. Mpgo.exe posibilita la generación y el consumo de datos de perfil para ensamblados de aplicación de imagen nativa (no los ensamblados de .NET Framework) mediante escenarios de aprendizaje seleccionados por el desarrollador de aplicaciones.

- [Ngen.exe (Generador de imágenes nativas)](ngen-exe-native-image-generator.md)  
Mejora el rendimiento de las aplicaciones administradas mediante el uso de imágenes nativas (archivos que contienen código máquina compilado específico del procesador). El runtime puede usar imágenes nativas de la memoria caché en lugar de usar el compilador Just-In-Time (JIT) para compilar el ensamblado original.

- [Peverify.exe (Herramienta PEVerify)](peverify-exe-peverify-tool.md)  
Le ayuda a comprobar si su código del lenguaje intermedio de Microsoft (MSIL) y los metadatos asociados cumplen los requisitos de seguridad de tipos.

- [Regasm.exe (Herramienta de registro de ensamblados)](regasm-exe-assembly-registration-tool.md)  
Lee los metadatos de un ensamblado y agrega las entradas necesarias al Registro. Esto permite a los clientes COM aparecer como clases de .NET Framework.

- [Regsvcs.exe (Herramienta de instalación de servicios de .NET)](regsvcs-exe-net-services-installation-tool.md)  
Carga y registra un ensamblado, genera e instala una biblioteca de tipos en una aplicación especificada de la versión de COM+ 1.0 y configura servicios que ha agregado a una clase mediante programación.

- [Resgen.exe (generador de archivos de recursos)](resgen-exe-resource-file-generator.md)  
Convierte archivos de texto ( *.txt* o *.restext*) y archivos de formato de recursos basado en XML ( *.resx*) en archivos binarios de Common Language Runtime ( *.resources*) que se pueden incrustar en un archivo ejecutable binario en tiempo de ejecución o compilar en ensamblados satélite.

- [SecAnnotate.exe (Herramienta Anotador de seguridad de .NET)](secannotate-exe-net-security-annotator-tool.md)  
Identifica las partes `SecurityCritical` y `SecuritySafeCritical` de un ensamblado.

- [SignTool.exe (Herramienta de firma)](signtool-exe.md)  
Firma digitalmente los archivos, comprueba las firmas de los mismos y les agrega una marca de tiempo.

- [Sn.exe (Herramienta de nombre seguro)](sn-exe-strong-name-tool.md)  
Ayuda a crear ensamblados con nombres seguros. Esta herramienta proporciona opciones para la administración de claves, así como para la generación y comprobación de firmas.

- [SOS.dll (Extensión de depuración de SOS)](sos-dll-sos-debugging-extension.md)  
Le ayuda a depurar programas administrados en el depurador WinDbg.exe y en Visual Studio al proporcionar información acerca del entorno interno de Common Language Runtime.

- [SqlMetal.exe (Herramienta de generación de código)](sqlmetal-exe-code-generation-tool.md)  
Genera código y asignaciones para el componente LINQ to SQL de .NET Framework.

- [Storeadm.exe (herramienta de almacenamiento aislado)](storeadm-exe-isolated-storage-tool.md)  
Administra el almacenamiento aislado; proporciona opciones para confeccionar una lista de los almacenes de usuario y eliminarlos.

- [Tlbexp.exe (Exportador de la biblioteca de tipos)](tlbexp-exe-type-library-exporter.md)  
Genera una biblioteca de tipos que describe los tipos definidos en un ensamblado de Common Language Runtime.

- [TlbImp.exe (Importador de la biblioteca de tipos)](tlbimp-exe-type-library-importer.md)  
Convierte las definiciones de tipos encontradas en una biblioteca de tipos COM en las definiciones equivalentes en un ensamblado de Common Language Runtime.

- [Winmdexp.exe (Herramienta de exportación de metadatos de Windows Runtime)](winmdexp-exe-windows-runtime-metadata-export-tool.md)  
Exporta un ensamblado de .NET Framework que se compila como un archivo *.winmdobj* en un componente de Windows Runtime, que se empaqueta como un archivo *.winmd* que contiene los metadatos y la información de implementación de Windows Runtime.

- [Winres.exe (Editor de recursos de Windows Forms)](winres-exe-windows-forms-resource-editor.md)  
Le ayuda a traducir recursos de la interfaz de usuario (IU) (archivos *.resx* o *.resources*) usados por Windows Forms. Puede traducir cadenas y, a continuación, ajustar el tamaño, mover y ocultar los controles para dar cabida a las cadenas traducidas.

## <a name="related-sections"></a>Secciones relacionadas

- [Herramientas de WPF](https://docs.microsoft.com/previous-versions/ms742404(v=vs.110))  
Incluye herramientas como la herramienta isXPS Conformance (isXPS.exe) y las herramientas de generación de perfiles de rendimiento.

- [Herramientas de Windows Communication Foundation](../wcf/tools.md)  
Incluye herramientas que facilitan la creación, implementación y administración de aplicaciones de Windows Communication Foundation (WCF).
