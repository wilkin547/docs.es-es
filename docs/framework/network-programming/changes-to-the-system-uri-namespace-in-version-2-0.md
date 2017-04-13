---
title: "Cambios realizados en el espacio de nombres System.Uri de la versi&#243;n 2.0 | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 35883fe9-2d09-4d8b-80ca-cf23a941e459
caps.latest.revision: 9
author: "mcleblanc"
ms.author: "markl"
manager: "markl"
caps.handback.revision: 9
---
# Cambios realizados en el espacio de nombres System.Uri de la versi&#243;n 2.0
Varios cambios se realizaron en la clase de <xref:System.Uri?displayProperty=fullName> .  Estos cambios corrigen un comportamiento incorrecto, utilidad mejorada, y ampliaron seguridad.  
  
## Miembros obsoletos y desusado  
 Constructores:  
  
-   Todos los constructores que tienen un parámetro de `dontEscape`.  
  
 Métodos:  
  
-   <xref:System.Uri.CheckSecurity%2A>  
  
-   <xref:System.Uri.Escape%2A>  
  
-   <xref:System.Uri.Canonicalize%2A>  
  
-   <xref:System.Uri.Parse%2A>  
  
-   <xref:System.Uri.IsReservedCharacter%2A>  
  
-   <xref:System.Uri.IsBadFileSystemCharacter%2A>  
  
-   <xref:System.Uri.IsExcludedCharacter%2A>  
  
-   <xref:System.Uri.EscapeString%2A>  
  
## Cambios  
  
-   Para esquemas de URI que se sabe que no tenga una parte de la consulta \(archivo, FTP, etc.\), “?” el carácter siempre se filtra y no se considera el principio de una parte de <xref:System.Uri.Query%2A> .  
  
-   Para los URI implícitos de archivo \(con el formato "c:\\directory\\file@name.txt"\), el carácter del fragmento \(“\# "\) se convierte siempre a menos que se solicita el unescaping completo o <xref:System.Uri.LocalPath%2A> es `true`.  
  
-   Compatibilidad hostname UNC se quitó; la especificación IDN para representar nombres de host internacionales se adoptada.  
  
-   <xref:System.Uri.LocalPath%2A> siempre devuelve una cadena completamente sin escape.  
  
-   ¿<xref:System.Uri.ToString%2A> no hace unescape como “% ASCII”, “? ”, o un carácter “\#”.  
  
-   <xref:System.Uri.Equals%2A> ahora incluye parte de <xref:System.Uri.Query%2A> en la comprobación de la igualdad.  
  
-   ¡“\=\=” De los operadores y “\! \=” son reemplazados y vinculados a <xref:System.Uri.Equals%2A> el método.  
  
-   <xref:System.Uri.IsLoopback%2A> ahora genera resultados coherentes.  
  
-   El URI “`file:///path`” se traduce ya no en “file:\/\/path”.  
  
-   “\#” ahora se reconoce como terminador del nombre de host.  Es decir, “http:\/\/consoto.com\#fragment” ahora se convierte en “http:\/\/contoso.com\/\#fragment”.  
  
-   Un error al combinar un URI base con un fragmento se ha corregido.  
  
-   Un error en <xref:System.Uri.HostNameType%2A> es fijo.  
  
-   Un error al analizar de NNTP es fijo.  
  
-   UN URI http del formulario: contoso.com ahora una excepción de análisis.  
  
-   El marco correctamente administra userinfo en un URI.  
  
-   Se corrige la compresión de ruta de acceso de URI de modo que un URI dañado no pueda recorrer el sistema de archivos a la raíz.  
  
## Vea también  
 <xref:System.Uri?displayProperty=fullName>