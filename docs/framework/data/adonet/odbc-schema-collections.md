---
title: Colecciones de esquemas de ODBC
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bb126a5-ceec-4649-a4bc-8aa19e801046
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 889e84db39af1257d709ef049e18d4397ea700d0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="6b59e-102">Colecciones de esquemas de ODBC</span><span class="sxs-lookup"><span data-stu-id="6b59e-102">ODBC Schema Collections</span></span>
<span data-ttu-id="6b59e-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los controladores ODBC de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="6b59e-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="6b59e-104">Controlador ODBC para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="6b59e-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="6b59e-105">El controlador ODBC de Microsoft SQL Server admite además las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="6b59e-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="6b59e-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="6b59e-106">Tables</span></span>  
  
-   <span data-ttu-id="6b59e-107">Índices</span><span class="sxs-lookup"><span data-stu-id="6b59e-107">Indexes</span></span>  
  
-   <span data-ttu-id="6b59e-108">Columnas</span><span class="sxs-lookup"><span data-stu-id="6b59e-108">Columns</span></span>  
  
-   <span data-ttu-id="6b59e-109">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="6b59e-109">Procedures</span></span>  
  
-   <span data-ttu-id="6b59e-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="6b59e-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="6b59e-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="6b59e-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="6b59e-112">Vistas</span><span class="sxs-lookup"><span data-stu-id="6b59e-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="6b59e-113">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="6b59e-113">Tables and Views</span></span>  
  
|<span data-ttu-id="6b59e-114">ColumName</span><span class="sxs-lookup"><span data-stu-id="6b59e-114">ColumnName</span></span>|<span data-ttu-id="6b59e-115">DataType</span><span class="sxs-lookup"><span data-stu-id="6b59e-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6b59e-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="6b59e-116">TABLE_CAT</span></span>|<span data-ttu-id="6b59e-117">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-117">String</span></span>|  
|<span data-ttu-id="6b59e-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="6b59e-118">TABLE_SCHEM</span></span>|<span data-ttu-id="6b59e-119">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-119">String</span></span>|  
|<span data-ttu-id="6b59e-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-120">TABLE_NAME</span></span>|<span data-ttu-id="6b59e-121">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-121">String</span></span>|  
|<span data-ttu-id="6b59e-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-122">TABLE_TYPE</span></span>|<span data-ttu-id="6b59e-123">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-123">String</span></span>|  
|<span data-ttu-id="6b59e-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="6b59e-124">REMARKS</span></span>|<span data-ttu-id="6b59e-125">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="6b59e-126">Índices</span><span class="sxs-lookup"><span data-stu-id="6b59e-126">Indexes</span></span>  
  
|<span data-ttu-id="6b59e-127">ColumName</span><span class="sxs-lookup"><span data-stu-id="6b59e-127">ColumnName</span></span>|<span data-ttu-id="6b59e-128">DataType</span><span class="sxs-lookup"><span data-stu-id="6b59e-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6b59e-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="6b59e-129">TABLE_CAT</span></span>|<span data-ttu-id="6b59e-130">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-130">String</span></span>|  
|<span data-ttu-id="6b59e-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="6b59e-131">TABLE_SCHEM</span></span>|<span data-ttu-id="6b59e-132">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-132">String</span></span>|  
|<span data-ttu-id="6b59e-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-133">TABLE_NAME</span></span>|<span data-ttu-id="6b59e-134">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-134">String</span></span>|  
|<span data-ttu-id="6b59e-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="6b59e-135">NON_UNIQUE</span></span>|<span data-ttu-id="6b59e-136">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-136">Int16</span></span>|  
|<span data-ttu-id="6b59e-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="6b59e-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="6b59e-138">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-138">String</span></span>|  
|<span data-ttu-id="6b59e-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-139">INDEX_NAME</span></span>|<span data-ttu-id="6b59e-140">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-140">String</span></span>|  
|<span data-ttu-id="6b59e-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-141">TYPE</span></span>|<span data-ttu-id="6b59e-142">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-142">Int16</span></span>|  
|<span data-ttu-id="6b59e-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6b59e-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="6b59e-144">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-144">Int16</span></span>|  
|<span data-ttu-id="6b59e-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-145">COLUMN_NAME</span></span>|<span data-ttu-id="6b59e-146">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-146">String</span></span>|  
|<span data-ttu-id="6b59e-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="6b59e-147">ASC_OR_DESC</span></span>|<span data-ttu-id="6b59e-148">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-148">String</span></span>|  
|<span data-ttu-id="6b59e-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="6b59e-149">CARDINATLITY</span></span>|<span data-ttu-id="6b59e-150">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-150">Int32</span></span>|  
|<span data-ttu-id="6b59e-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="6b59e-151">PAGES</span></span>|<span data-ttu-id="6b59e-152">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-152">Int32</span></span>|  
|<span data-ttu-id="6b59e-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="6b59e-153">FILTER_CONDITION</span></span>|<span data-ttu-id="6b59e-154">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-154">String</span></span>|  
|<span data-ttu-id="6b59e-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6b59e-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="6b59e-156">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-156">String</span></span>|  
|<span data-ttu-id="6b59e-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="6b59e-158">Byte</span><span class="sxs-lookup"><span data-stu-id="6b59e-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="6b59e-159">Columnas</span><span class="sxs-lookup"><span data-stu-id="6b59e-159">Columns</span></span>  
  
|<span data-ttu-id="6b59e-160">ColumName</span><span class="sxs-lookup"><span data-stu-id="6b59e-160">ColumnName</span></span>|<span data-ttu-id="6b59e-161">DataType</span><span class="sxs-lookup"><span data-stu-id="6b59e-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6b59e-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="6b59e-162">TABLE_CAT</span></span>|<span data-ttu-id="6b59e-163">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-163">String</span></span>|  
|<span data-ttu-id="6b59e-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="6b59e-164">TABLE_SCHEM</span></span>|<span data-ttu-id="6b59e-165">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-165">String</span></span>|  
|<span data-ttu-id="6b59e-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-166">TABLE_NAME</span></span>|<span data-ttu-id="6b59e-167">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-167">String</span></span>|  
|<span data-ttu-id="6b59e-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-168">COLUMN_NAME</span></span>|<span data-ttu-id="6b59e-169">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-169">String</span></span>|  
|<span data-ttu-id="6b59e-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-170">DATA_TYPE</span></span>|<span data-ttu-id="6b59e-171">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-171">Int16</span></span>|  
|<span data-ttu-id="6b59e-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-172">TYPE_NAME</span></span>|<span data-ttu-id="6b59e-173">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-173">String</span></span>|  
|<span data-ttu-id="6b59e-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="6b59e-174">COLUMN_SIZE</span></span>|<span data-ttu-id="6b59e-175">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-175">Int32</span></span>|  
|<span data-ttu-id="6b59e-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6b59e-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="6b59e-177">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-177">Int32</span></span>|  
|<span data-ttu-id="6b59e-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="6b59e-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="6b59e-179">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-179">Int16</span></span>|  
|<span data-ttu-id="6b59e-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="6b59e-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="6b59e-181">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-181">Int16</span></span>|  
|<span data-ttu-id="6b59e-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6b59e-182">NULLABLE</span></span>|<span data-ttu-id="6b59e-183">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-183">Int16</span></span>|  
|<span data-ttu-id="6b59e-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="6b59e-184">REMARKS</span></span>|<span data-ttu-id="6b59e-185">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-185">String</span></span>|  
|<span data-ttu-id="6b59e-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="6b59e-186">COLUMN_DEF</span></span>|<span data-ttu-id="6b59e-187">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-187">String</span></span>|  
|<span data-ttu-id="6b59e-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="6b59e-189">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-189">Int16</span></span>|  
|<span data-ttu-id="6b59e-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="6b59e-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="6b59e-191">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-191">Int16</span></span>|  
|<span data-ttu-id="6b59e-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6b59e-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="6b59e-193">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-193">Int32</span></span>|  
|<span data-ttu-id="6b59e-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6b59e-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="6b59e-195">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-195">Int32</span></span>|  
|<span data-ttu-id="6b59e-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6b59e-196">IS_NULLABLE</span></span>|<span data-ttu-id="6b59e-197">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-197">String</span></span>|  
|<span data-ttu-id="6b59e-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6b59e-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="6b59e-199">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-199">String</span></span>|  
|<span data-ttu-id="6b59e-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6b59e-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="6b59e-201">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-201">String</span></span>|  
|<span data-ttu-id="6b59e-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="6b59e-203">Byte</span><span class="sxs-lookup"><span data-stu-id="6b59e-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="6b59e-204">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="6b59e-204">Procedures</span></span>  
  
|<span data-ttu-id="6b59e-205">ColumName</span><span class="sxs-lookup"><span data-stu-id="6b59e-205">ColumnName</span></span>|<span data-ttu-id="6b59e-206">DataType</span><span class="sxs-lookup"><span data-stu-id="6b59e-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6b59e-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="6b59e-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="6b59e-208">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-208">String</span></span>|  
|<span data-ttu-id="6b59e-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="6b59e-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="6b59e-210">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-210">String</span></span>|  
|<span data-ttu-id="6b59e-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="6b59e-212">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-212">String</span></span>|  
|<span data-ttu-id="6b59e-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="6b59e-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="6b59e-214">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-214">Int32</span></span>|  
|<span data-ttu-id="6b59e-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="6b59e-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="6b59e-216">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-216">Int32</span></span>|  
|<span data-ttu-id="6b59e-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="6b59e-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="6b59e-218">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-218">Int32</span></span>|  
|<span data-ttu-id="6b59e-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="6b59e-219">REMARKS</span></span>|<span data-ttu-id="6b59e-220">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-220">String</span></span>|  
|<span data-ttu-id="6b59e-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="6b59e-222">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="6b59e-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="6b59e-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="6b59e-224">ColumName</span><span class="sxs-lookup"><span data-stu-id="6b59e-224">ColumnName</span></span>|<span data-ttu-id="6b59e-225">DataType</span><span class="sxs-lookup"><span data-stu-id="6b59e-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6b59e-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="6b59e-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="6b59e-227">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-227">String</span></span>|  
|<span data-ttu-id="6b59e-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="6b59e-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="6b59e-229">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-229">String</span></span>|  
|<span data-ttu-id="6b59e-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="6b59e-231">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-231">String</span></span>|  
|<span data-ttu-id="6b59e-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-232">COLUMN_NAME</span></span>|<span data-ttu-id="6b59e-233">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-233">String</span></span>|  
|<span data-ttu-id="6b59e-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-234">COLUMN_TYPE</span></span>|<span data-ttu-id="6b59e-235">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-235">Int16</span></span>|  
|<span data-ttu-id="6b59e-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-236">DATA_TYPE</span></span>|<span data-ttu-id="6b59e-237">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-237">Int16</span></span>|  
|<span data-ttu-id="6b59e-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-238">TYPE_NAME</span></span>|<span data-ttu-id="6b59e-239">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-239">String</span></span>|  
|<span data-ttu-id="6b59e-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="6b59e-240">COLUMN_SIZE</span></span>|<span data-ttu-id="6b59e-241">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-241">Int32</span></span>|  
|<span data-ttu-id="6b59e-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6b59e-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="6b59e-243">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-243">Int32</span></span>|  
|<span data-ttu-id="6b59e-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="6b59e-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="6b59e-245">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-245">Int16</span></span>|  
|<span data-ttu-id="6b59e-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="6b59e-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="6b59e-247">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-247">Int16</span></span>|  
|<span data-ttu-id="6b59e-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6b59e-248">NULLABLE</span></span>|<span data-ttu-id="6b59e-249">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-249">Int16</span></span>|  
|<span data-ttu-id="6b59e-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="6b59e-250">REMARKS</span></span>|<span data-ttu-id="6b59e-251">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-251">String</span></span>|  
|<span data-ttu-id="6b59e-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="6b59e-252">COLUMN_DEF</span></span>|<span data-ttu-id="6b59e-253">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-253">String</span></span>|  
|<span data-ttu-id="6b59e-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="6b59e-255">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-255">Int16</span></span>|  
|<span data-ttu-id="6b59e-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="6b59e-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="6b59e-257">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-257">Int16</span></span>|  
|<span data-ttu-id="6b59e-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6b59e-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="6b59e-259">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-259">Int32</span></span>|  
|<span data-ttu-id="6b59e-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6b59e-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="6b59e-261">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-261">Int32</span></span>|  
|<span data-ttu-id="6b59e-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6b59e-262">IS_NULLABLE</span></span>|<span data-ttu-id="6b59e-263">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-263">String</span></span>|  
|<span data-ttu-id="6b59e-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6b59e-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="6b59e-265">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-265">String</span></span>|  
|<span data-ttu-id="6b59e-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6b59e-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="6b59e-267">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-267">String</span></span>|  
|<span data-ttu-id="6b59e-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="6b59e-269">Byte</span><span class="sxs-lookup"><span data-stu-id="6b59e-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="6b59e-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="6b59e-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="6b59e-271">ColumName</span><span class="sxs-lookup"><span data-stu-id="6b59e-271">ColumnName</span></span>|<span data-ttu-id="6b59e-272">DataType</span><span class="sxs-lookup"><span data-stu-id="6b59e-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6b59e-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="6b59e-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="6b59e-274">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-274">String</span></span>|  
|<span data-ttu-id="6b59e-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="6b59e-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="6b59e-276">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-276">String</span></span>|  
|<span data-ttu-id="6b59e-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="6b59e-278">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-278">String</span></span>|  
|<span data-ttu-id="6b59e-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-279">COLUMN_NAME</span></span>|<span data-ttu-id="6b59e-280">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-280">String</span></span>|  
|<span data-ttu-id="6b59e-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-281">COLUMN_TYPE</span></span>|<span data-ttu-id="6b59e-282">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-282">Int16</span></span>|  
|<span data-ttu-id="6b59e-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-283">DATA_TYPE</span></span>|<span data-ttu-id="6b59e-284">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-284">Int16</span></span>|  
|<span data-ttu-id="6b59e-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-285">TYPE_NAME</span></span>|<span data-ttu-id="6b59e-286">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-286">String</span></span>|  
|<span data-ttu-id="6b59e-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="6b59e-287">COLUMN_SIZE</span></span>|<span data-ttu-id="6b59e-288">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-288">Int32</span></span>|  
|<span data-ttu-id="6b59e-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6b59e-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="6b59e-290">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-290">Int32</span></span>|  
|<span data-ttu-id="6b59e-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="6b59e-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="6b59e-292">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-292">Int16</span></span>|  
|<span data-ttu-id="6b59e-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="6b59e-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="6b59e-294">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-294">Int16</span></span>|  
|<span data-ttu-id="6b59e-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6b59e-295">NULLABLE</span></span>|<span data-ttu-id="6b59e-296">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-296">Int16</span></span>|  
|<span data-ttu-id="6b59e-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="6b59e-297">REMARKS</span></span>|<span data-ttu-id="6b59e-298">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-298">String</span></span>|  
|<span data-ttu-id="6b59e-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="6b59e-299">COLUMN_DEF</span></span>|<span data-ttu-id="6b59e-300">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-300">String</span></span>|  
|<span data-ttu-id="6b59e-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="6b59e-302">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-302">Int16</span></span>|  
|<span data-ttu-id="6b59e-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="6b59e-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="6b59e-304">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-304">Int16</span></span>|  
|<span data-ttu-id="6b59e-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6b59e-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="6b59e-306">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-306">Int32</span></span>|  
|<span data-ttu-id="6b59e-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6b59e-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="6b59e-308">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-308">Int32</span></span>|  
|<span data-ttu-id="6b59e-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6b59e-309">IS_NULLABLE</span></span>|<span data-ttu-id="6b59e-310">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-310">String</span></span>|  
|<span data-ttu-id="6b59e-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="6b59e-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="6b59e-312">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-312">String</span></span>|  
|<span data-ttu-id="6b59e-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="6b59e-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="6b59e-314">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-314">String</span></span>|  
|<span data-ttu-id="6b59e-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="6b59e-316">Byte</span><span class="sxs-lookup"><span data-stu-id="6b59e-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="6b59e-317">Controlador ODBC para Oracle de Microsoft</span><span class="sxs-lookup"><span data-stu-id="6b59e-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="6b59e-318">El controlador ODBC de Oracle de Microsoft SQL Server admite además las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="6b59e-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="6b59e-319">Tablas</span><span class="sxs-lookup"><span data-stu-id="6b59e-319">Tables</span></span>  
  
-   <span data-ttu-id="6b59e-320">Columnas</span><span class="sxs-lookup"><span data-stu-id="6b59e-320">Columns</span></span>  
  
-   <span data-ttu-id="6b59e-321">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="6b59e-321">Procedures</span></span>  
  
-   <span data-ttu-id="6b59e-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="6b59e-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="6b59e-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="6b59e-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="6b59e-324">Vistas</span><span class="sxs-lookup"><span data-stu-id="6b59e-324">Views</span></span>  
  
-   <span data-ttu-id="6b59e-325">Índices</span><span class="sxs-lookup"><span data-stu-id="6b59e-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="6b59e-326">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="6b59e-326">Tables and Views</span></span>  
  
|<span data-ttu-id="6b59e-327">ColumName</span><span class="sxs-lookup"><span data-stu-id="6b59e-327">ColumnName</span></span>|<span data-ttu-id="6b59e-328">DataType</span><span class="sxs-lookup"><span data-stu-id="6b59e-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6b59e-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="6b59e-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="6b59e-330">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-330">String</span></span>|  
|<span data-ttu-id="6b59e-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="6b59e-331">TABLE_OWNER</span></span>|<span data-ttu-id="6b59e-332">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-332">String</span></span>|  
|<span data-ttu-id="6b59e-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-333">TABLE_NAME</span></span>|<span data-ttu-id="6b59e-334">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-334">String</span></span>|  
|<span data-ttu-id="6b59e-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-335">TABLE_TYPE</span></span>|<span data-ttu-id="6b59e-336">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-336">String</span></span>|  
|<span data-ttu-id="6b59e-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="6b59e-337">REMARKS</span></span>|<span data-ttu-id="6b59e-338">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="6b59e-339">Columnas</span><span class="sxs-lookup"><span data-stu-id="6b59e-339">Columns</span></span>  
  
|<span data-ttu-id="6b59e-340">ColumName</span><span class="sxs-lookup"><span data-stu-id="6b59e-340">ColumnName</span></span>|<span data-ttu-id="6b59e-341">DataType</span><span class="sxs-lookup"><span data-stu-id="6b59e-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6b59e-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="6b59e-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="6b59e-343">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-343">String</span></span>|  
|<span data-ttu-id="6b59e-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="6b59e-344">TABLE_OWNER</span></span>|<span data-ttu-id="6b59e-345">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-345">String</span></span>|  
|<span data-ttu-id="6b59e-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-346">TABLE_NAME</span></span>|<span data-ttu-id="6b59e-347">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-347">String</span></span>|  
|<span data-ttu-id="6b59e-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-348">COLUMN_NAME</span></span>|<span data-ttu-id="6b59e-349">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-349">String</span></span>|  
|<span data-ttu-id="6b59e-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-350">DATA_TYPE</span></span>|<span data-ttu-id="6b59e-351">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-351">Int16</span></span>|  
|<span data-ttu-id="6b59e-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-352">TYPE_NAME</span></span>|<span data-ttu-id="6b59e-353">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-353">String</span></span>|  
|<span data-ttu-id="6b59e-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="6b59e-354">PRECISION</span></span>|<span data-ttu-id="6b59e-355">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-355">Int32</span></span>|  
|<span data-ttu-id="6b59e-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="6b59e-356">LENGTH</span></span>|<span data-ttu-id="6b59e-357">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-357">Int32</span></span>|  
|<span data-ttu-id="6b59e-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="6b59e-358">SCALE</span></span>|<span data-ttu-id="6b59e-359">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-359">Int16</span></span>|  
|<span data-ttu-id="6b59e-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="6b59e-360">RADIX</span></span>|<span data-ttu-id="6b59e-361">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-361">Int16</span></span>|  
|<span data-ttu-id="6b59e-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6b59e-362">NULLABLE</span></span>|<span data-ttu-id="6b59e-363">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-363">Int16</span></span>|  
|<span data-ttu-id="6b59e-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="6b59e-364">REMARKS</span></span>|<span data-ttu-id="6b59e-365">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-365">String</span></span>|  
|<span data-ttu-id="6b59e-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6b59e-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="6b59e-367">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="6b59e-368">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="6b59e-368">Procedures</span></span>  
  
|<span data-ttu-id="6b59e-369">ColumName</span><span class="sxs-lookup"><span data-stu-id="6b59e-369">ColumnName</span></span>|<span data-ttu-id="6b59e-370">DataType</span><span class="sxs-lookup"><span data-stu-id="6b59e-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6b59e-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="6b59e-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="6b59e-372">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-372">String</span></span>|  
|<span data-ttu-id="6b59e-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="6b59e-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="6b59e-374">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-374">String</span></span>|  
|<span data-ttu-id="6b59e-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="6b59e-376">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-376">String</span></span>|  
|<span data-ttu-id="6b59e-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="6b59e-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="6b59e-378">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-378">Int16</span></span>|  
|<span data-ttu-id="6b59e-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="6b59e-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="6b59e-380">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-380">Int16</span></span>|  
|<span data-ttu-id="6b59e-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="6b59e-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="6b59e-382">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-382">Int16</span></span>|  
|<span data-ttu-id="6b59e-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="6b59e-383">REMARKS</span></span>|<span data-ttu-id="6b59e-384">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-384">String</span></span>|  
|<span data-ttu-id="6b59e-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="6b59e-386">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="6b59e-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="6b59e-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="6b59e-388">ColumName</span><span class="sxs-lookup"><span data-stu-id="6b59e-388">ColumnName</span></span>|<span data-ttu-id="6b59e-389">DataType</span><span class="sxs-lookup"><span data-stu-id="6b59e-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6b59e-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="6b59e-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="6b59e-391">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-391">String</span></span>|  
|<span data-ttu-id="6b59e-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="6b59e-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="6b59e-393">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-393">String</span></span>|  
|<span data-ttu-id="6b59e-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="6b59e-395">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-395">String</span></span>|  
|<span data-ttu-id="6b59e-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-396">COLUMN_NAME</span></span>|<span data-ttu-id="6b59e-397">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-397">String</span></span>|  
|<span data-ttu-id="6b59e-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-398">COLUMN_TYPE</span></span>|<span data-ttu-id="6b59e-399">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-399">Int16</span></span>|  
|<span data-ttu-id="6b59e-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-400">DATA_TYPE</span></span>|<span data-ttu-id="6b59e-401">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-401">Int16</span></span>|  
|<span data-ttu-id="6b59e-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-402">TYPE_NAME</span></span>|<span data-ttu-id="6b59e-403">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-403">String</span></span>|  
|<span data-ttu-id="6b59e-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="6b59e-404">PRECISION</span></span>|<span data-ttu-id="6b59e-405">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-405">Int32</span></span>|  
|<span data-ttu-id="6b59e-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="6b59e-406">LENGTH</span></span>|<span data-ttu-id="6b59e-407">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-407">Int32</span></span>|  
|<span data-ttu-id="6b59e-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="6b59e-408">SCALE</span></span>|<span data-ttu-id="6b59e-409">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-409">Int16</span></span>|  
|<span data-ttu-id="6b59e-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="6b59e-410">RADIX</span></span>|<span data-ttu-id="6b59e-411">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-411">Int16</span></span>|  
|<span data-ttu-id="6b59e-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6b59e-412">NULLABLE</span></span>|<span data-ttu-id="6b59e-413">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-413">Int16</span></span>|  
|<span data-ttu-id="6b59e-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="6b59e-414">REMARKS</span></span>|<span data-ttu-id="6b59e-415">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-415">String</span></span>|  
|<span data-ttu-id="6b59e-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="6b59e-416">OVERLOAD</span></span>|<span data-ttu-id="6b59e-417">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-417">Int32</span></span>|  
|<span data-ttu-id="6b59e-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6b59e-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="6b59e-419">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="6b59e-420">Controlador ODBC de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="6b59e-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="6b59e-421">El controlador ODBC de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="6b59e-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="6b59e-422">Tablas</span><span class="sxs-lookup"><span data-stu-id="6b59e-422">Tables</span></span>  
  
-   <span data-ttu-id="6b59e-423">Índices</span><span class="sxs-lookup"><span data-stu-id="6b59e-423">Indexes</span></span>  
  
-   <span data-ttu-id="6b59e-424">Columnas</span><span class="sxs-lookup"><span data-stu-id="6b59e-424">Columns</span></span>  
  
-   <span data-ttu-id="6b59e-425">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="6b59e-425">Procedures</span></span>  
  
-   <span data-ttu-id="6b59e-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="6b59e-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="6b59e-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="6b59e-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="6b59e-428">Vistas</span><span class="sxs-lookup"><span data-stu-id="6b59e-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="6b59e-429">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="6b59e-429">Tables and Views</span></span>  
  
|<span data-ttu-id="6b59e-430">ColumName</span><span class="sxs-lookup"><span data-stu-id="6b59e-430">ColumnName</span></span>|<span data-ttu-id="6b59e-431">DataType</span><span class="sxs-lookup"><span data-stu-id="6b59e-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6b59e-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="6b59e-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="6b59e-433">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-433">String</span></span>|  
|<span data-ttu-id="6b59e-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="6b59e-434">TABLE_OWNER</span></span>|<span data-ttu-id="6b59e-435">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-435">String</span></span>|  
|<span data-ttu-id="6b59e-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-436">TABLE_NAME</span></span>|<span data-ttu-id="6b59e-437">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-437">String</span></span>|  
|<span data-ttu-id="6b59e-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-438">TABLE_TYPE</span></span>|<span data-ttu-id="6b59e-439">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-439">String</span></span>|  
|<span data-ttu-id="6b59e-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="6b59e-440">REMARKS</span></span>|<span data-ttu-id="6b59e-441">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="6b59e-442">Columnas</span><span class="sxs-lookup"><span data-stu-id="6b59e-442">Columns</span></span>  
  
|<span data-ttu-id="6b59e-443">ColumName</span><span class="sxs-lookup"><span data-stu-id="6b59e-443">ColumnName</span></span>|<span data-ttu-id="6b59e-444">DataType</span><span class="sxs-lookup"><span data-stu-id="6b59e-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6b59e-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="6b59e-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="6b59e-446">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-446">String</span></span>|  
|<span data-ttu-id="6b59e-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="6b59e-447">TABLE_OWNER</span></span>|<span data-ttu-id="6b59e-448">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-448">String</span></span>|  
|<span data-ttu-id="6b59e-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-449">TABLE_NAME</span></span>|<span data-ttu-id="6b59e-450">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-450">String</span></span>|  
|<span data-ttu-id="6b59e-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-451">COLUMN_NAME</span></span>|<span data-ttu-id="6b59e-452">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-452">String</span></span>|  
|<span data-ttu-id="6b59e-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-453">DATA_TYPE</span></span>|<span data-ttu-id="6b59e-454">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-454">Int16</span></span>|  
|<span data-ttu-id="6b59e-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-455">TYPE_NAME</span></span>|<span data-ttu-id="6b59e-456">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-456">String</span></span>|  
|<span data-ttu-id="6b59e-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="6b59e-457">PRECISION</span></span>|<span data-ttu-id="6b59e-458">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-458">Int32</span></span>|  
|<span data-ttu-id="6b59e-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="6b59e-459">LENGTH</span></span>|<span data-ttu-id="6b59e-460">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-460">Int32</span></span>|  
|<span data-ttu-id="6b59e-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="6b59e-461">SCALE</span></span>|<span data-ttu-id="6b59e-462">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-462">Int16</span></span>|  
|<span data-ttu-id="6b59e-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="6b59e-463">RADIX</span></span>|<span data-ttu-id="6b59e-464">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-464">Int16</span></span>|  
|<span data-ttu-id="6b59e-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6b59e-465">NULLABLE</span></span>|<span data-ttu-id="6b59e-466">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-466">Int16</span></span>|  
|<span data-ttu-id="6b59e-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="6b59e-467">REMARKS</span></span>|<span data-ttu-id="6b59e-468">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-468">String</span></span>|  
|<span data-ttu-id="6b59e-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6b59e-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="6b59e-470">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="6b59e-471">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="6b59e-471">Procedures</span></span>  
  
|<span data-ttu-id="6b59e-472">ColumName</span><span class="sxs-lookup"><span data-stu-id="6b59e-472">ColumnName</span></span>|<span data-ttu-id="6b59e-473">DataType</span><span class="sxs-lookup"><span data-stu-id="6b59e-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6b59e-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="6b59e-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="6b59e-475">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-475">String</span></span>|  
|<span data-ttu-id="6b59e-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="6b59e-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="6b59e-477">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-477">String</span></span>|  
|<span data-ttu-id="6b59e-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="6b59e-479">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-479">String</span></span>|  
|<span data-ttu-id="6b59e-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="6b59e-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="6b59e-481">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-481">Int16</span></span>|  
|<span data-ttu-id="6b59e-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="6b59e-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="6b59e-483">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-483">Int16</span></span>|  
|<span data-ttu-id="6b59e-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="6b59e-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="6b59e-485">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-485">Int16</span></span>|  
|<span data-ttu-id="6b59e-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="6b59e-486">REMARKS</span></span>|<span data-ttu-id="6b59e-487">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-487">String</span></span>|  
|<span data-ttu-id="6b59e-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="6b59e-489">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="6b59e-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="6b59e-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="6b59e-491">ColumName</span><span class="sxs-lookup"><span data-stu-id="6b59e-491">ColumnName</span></span>|<span data-ttu-id="6b59e-492">DataType</span><span class="sxs-lookup"><span data-stu-id="6b59e-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6b59e-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="6b59e-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="6b59e-494">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-494">String</span></span>|  
|<span data-ttu-id="6b59e-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="6b59e-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="6b59e-496">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-496">String</span></span>|  
|<span data-ttu-id="6b59e-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="6b59e-498">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-498">String</span></span>|  
|<span data-ttu-id="6b59e-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-499">COLUMN_NAME</span></span>|<span data-ttu-id="6b59e-500">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-500">String</span></span>|  
|<span data-ttu-id="6b59e-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-501">COLUMN_TYPE</span></span>|<span data-ttu-id="6b59e-502">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-502">Int16</span></span>|  
|<span data-ttu-id="6b59e-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-503">DATA_TYPE</span></span>|<span data-ttu-id="6b59e-504">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-504">Int16</span></span>|  
|<span data-ttu-id="6b59e-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-505">TYPE_NAME</span></span>|<span data-ttu-id="6b59e-506">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-506">String</span></span>|  
|<span data-ttu-id="6b59e-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="6b59e-507">PRECISION</span></span>|<span data-ttu-id="6b59e-508">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-508">Int32</span></span>|  
|<span data-ttu-id="6b59e-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="6b59e-509">LENGTH</span></span>|<span data-ttu-id="6b59e-510">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-510">Int32</span></span>|  
|<span data-ttu-id="6b59e-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="6b59e-511">SCALE</span></span>|<span data-ttu-id="6b59e-512">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-512">Int16</span></span>|  
|<span data-ttu-id="6b59e-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="6b59e-513">RADIX</span></span>|<span data-ttu-id="6b59e-514">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-514">Int16</span></span>|  
|<span data-ttu-id="6b59e-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6b59e-515">NULLABLE</span></span>|<span data-ttu-id="6b59e-516">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-516">Int16</span></span>|  
|<span data-ttu-id="6b59e-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="6b59e-517">REMARKS</span></span>|<span data-ttu-id="6b59e-518">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-518">String</span></span>|  
|<span data-ttu-id="6b59e-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="6b59e-519">OVERLOAD</span></span>|<span data-ttu-id="6b59e-520">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-520">Int32</span></span>|  
|<span data-ttu-id="6b59e-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6b59e-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="6b59e-522">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="6b59e-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="6b59e-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="6b59e-524">ColumName</span><span class="sxs-lookup"><span data-stu-id="6b59e-524">ColumnName</span></span>|<span data-ttu-id="6b59e-525">DataType</span><span class="sxs-lookup"><span data-stu-id="6b59e-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="6b59e-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="6b59e-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="6b59e-527">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-527">String</span></span>|  
|<span data-ttu-id="6b59e-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="6b59e-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="6b59e-529">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-529">String</span></span>|  
|<span data-ttu-id="6b59e-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="6b59e-531">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-531">String</span></span>|  
|<span data-ttu-id="6b59e-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-532">COLUMN_NAME</span></span>|<span data-ttu-id="6b59e-533">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-533">String</span></span>|  
|<span data-ttu-id="6b59e-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-534">COLUMN_TYPE</span></span>|<span data-ttu-id="6b59e-535">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-535">Int16</span></span>|  
|<span data-ttu-id="6b59e-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-536">DATA_TYPE</span></span>|<span data-ttu-id="6b59e-537">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-537">Int16</span></span>|  
|<span data-ttu-id="6b59e-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="6b59e-538">TYPE_NAME</span></span>|<span data-ttu-id="6b59e-539">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-539">String</span></span>|  
|<span data-ttu-id="6b59e-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="6b59e-540">COLUMN_SIZE</span></span>|<span data-ttu-id="6b59e-541">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-541">Int32</span></span>|  
|<span data-ttu-id="6b59e-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6b59e-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="6b59e-543">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-543">Int32</span></span>|  
|<span data-ttu-id="6b59e-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="6b59e-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="6b59e-545">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-545">Int16</span></span>|  
|<span data-ttu-id="6b59e-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="6b59e-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="6b59e-547">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-547">Int16</span></span>|  
|<span data-ttu-id="6b59e-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6b59e-548">NULLABLE</span></span>|<span data-ttu-id="6b59e-549">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-549">Int16</span></span>|  
|<span data-ttu-id="6b59e-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="6b59e-550">REMARKS</span></span>|<span data-ttu-id="6b59e-551">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-551">String</span></span>|  
|<span data-ttu-id="6b59e-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="6b59e-552">COLUMN_DEF</span></span>|<span data-ttu-id="6b59e-553">String</span><span class="sxs-lookup"><span data-stu-id="6b59e-553">String</span></span>|  
|<span data-ttu-id="6b59e-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="6b59e-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="6b59e-555">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-555">Int16</span></span>|  
|<span data-ttu-id="6b59e-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="6b59e-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="6b59e-557">Int16</span><span class="sxs-lookup"><span data-stu-id="6b59e-557">Int16</span></span>|  
|<span data-ttu-id="6b59e-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="6b59e-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="6b59e-559">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-559">Int32</span></span>|  
|<span data-ttu-id="6b59e-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="6b59e-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="6b59e-561">Int32</span><span class="sxs-lookup"><span data-stu-id="6b59e-561">Int32</span></span>|  
|<span data-ttu-id="6b59e-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="6b59e-562">IS_NULLABLE</span></span>|<span data-ttu-id="6b59e-563">Cadena</span><span class="sxs-lookup"><span data-stu-id="6b59e-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6b59e-564">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b59e-564">See Also</span></span>  
 [<span data-ttu-id="6b59e-565">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="6b59e-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
