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
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 45cfed80decc2336c5a2bacf24fd075c2b81c531
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2018
---
# <a name="odbc-schema-collections"></a><span data-ttu-id="42c6f-102">Colecciones de esquemas de ODBC</span><span class="sxs-lookup"><span data-stu-id="42c6f-102">ODBC Schema Collections</span></span>
<span data-ttu-id="42c6f-103">En esta sección se describe la compatibilidad de las colecciones de esquemas con los controladores ODBC de Microsoft SQL Server, Oracle y Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="42c6f-103">This section discusses schema collection support for the ODBC drivers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-odbc-driver"></a><span data-ttu-id="42c6f-104">Controlador ODBC para Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="42c6f-104">Microsoft SQL Server ODBC Driver</span></span>  
 <span data-ttu-id="42c6f-105">El controlador ODBC de Microsoft SQL Server admite además las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="42c6f-105">The Microsoft SQL Server ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="42c6f-106">Tablas</span><span class="sxs-lookup"><span data-stu-id="42c6f-106">Tables</span></span>  
  
-   <span data-ttu-id="42c6f-107">Índices</span><span class="sxs-lookup"><span data-stu-id="42c6f-107">Indexes</span></span>  
  
-   <span data-ttu-id="42c6f-108">Columnas</span><span class="sxs-lookup"><span data-stu-id="42c6f-108">Columns</span></span>  
  
-   <span data-ttu-id="42c6f-109">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="42c6f-109">Procedures</span></span>  
  
-   <span data-ttu-id="42c6f-110">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="42c6f-110">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="42c6f-111">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="42c6f-111">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="42c6f-112">Vistas</span><span class="sxs-lookup"><span data-stu-id="42c6f-112">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="42c6f-113">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="42c6f-113">Tables and Views</span></span>  
  
|<span data-ttu-id="42c6f-114">ColumName</span><span class="sxs-lookup"><span data-stu-id="42c6f-114">ColumnName</span></span>|<span data-ttu-id="42c6f-115">DataType</span><span class="sxs-lookup"><span data-stu-id="42c6f-115">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="42c6f-116">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="42c6f-116">TABLE_CAT</span></span>|<span data-ttu-id="42c6f-117">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-117">String</span></span>|  
|<span data-ttu-id="42c6f-118">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="42c6f-118">TABLE_SCHEM</span></span>|<span data-ttu-id="42c6f-119">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-119">String</span></span>|  
|<span data-ttu-id="42c6f-120">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-120">TABLE_NAME</span></span>|<span data-ttu-id="42c6f-121">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-121">String</span></span>|  
|<span data-ttu-id="42c6f-122">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-122">TABLE_TYPE</span></span>|<span data-ttu-id="42c6f-123">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-123">String</span></span>|  
|<span data-ttu-id="42c6f-124">REMARKS</span><span class="sxs-lookup"><span data-stu-id="42c6f-124">REMARKS</span></span>|<span data-ttu-id="42c6f-125">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-125">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="42c6f-126">Índices</span><span class="sxs-lookup"><span data-stu-id="42c6f-126">Indexes</span></span>  
  
|<span data-ttu-id="42c6f-127">ColumName</span><span class="sxs-lookup"><span data-stu-id="42c6f-127">ColumnName</span></span>|<span data-ttu-id="42c6f-128">DataType</span><span class="sxs-lookup"><span data-stu-id="42c6f-128">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="42c6f-129">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="42c6f-129">TABLE_CAT</span></span>|<span data-ttu-id="42c6f-130">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-130">String</span></span>|  
|<span data-ttu-id="42c6f-131">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="42c6f-131">TABLE_SCHEM</span></span>|<span data-ttu-id="42c6f-132">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-132">String</span></span>|  
|<span data-ttu-id="42c6f-133">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-133">TABLE_NAME</span></span>|<span data-ttu-id="42c6f-134">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-134">String</span></span>|  
|<span data-ttu-id="42c6f-135">NON_UNIQUE</span><span class="sxs-lookup"><span data-stu-id="42c6f-135">NON_UNIQUE</span></span>|<span data-ttu-id="42c6f-136">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-136">Int16</span></span>|  
|<span data-ttu-id="42c6f-137">INDEX_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="42c6f-137">INDEX_QUALIFIER</span></span>|<span data-ttu-id="42c6f-138">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-138">String</span></span>|  
|<span data-ttu-id="42c6f-139">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-139">INDEX_NAME</span></span>|<span data-ttu-id="42c6f-140">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-140">String</span></span>|  
|<span data-ttu-id="42c6f-141">TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-141">TYPE</span></span>|<span data-ttu-id="42c6f-142">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-142">Int16</span></span>|  
|<span data-ttu-id="42c6f-143">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="42c6f-143">ORDINAL_POSITION</span></span>|<span data-ttu-id="42c6f-144">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-144">Int16</span></span>|  
|<span data-ttu-id="42c6f-145">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-145">COLUMN_NAME</span></span>|<span data-ttu-id="42c6f-146">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-146">String</span></span>|  
|<span data-ttu-id="42c6f-147">ASC_OR_DESC</span><span class="sxs-lookup"><span data-stu-id="42c6f-147">ASC_OR_DESC</span></span>|<span data-ttu-id="42c6f-148">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-148">String</span></span>|  
|<span data-ttu-id="42c6f-149">CARDINATLITY</span><span class="sxs-lookup"><span data-stu-id="42c6f-149">CARDINATLITY</span></span>|<span data-ttu-id="42c6f-150">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-150">Int32</span></span>|  
|<span data-ttu-id="42c6f-151">PAGES</span><span class="sxs-lookup"><span data-stu-id="42c6f-151">PAGES</span></span>|<span data-ttu-id="42c6f-152">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-152">Int32</span></span>|  
|<span data-ttu-id="42c6f-153">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="42c6f-153">FILTER_CONDITION</span></span>|<span data-ttu-id="42c6f-154">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-154">String</span></span>|  
|<span data-ttu-id="42c6f-155">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="42c6f-155">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="42c6f-156">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-156">String</span></span>|  
|<span data-ttu-id="42c6f-157">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-157">SS_DATA_TYPE</span></span>|<span data-ttu-id="42c6f-158">Byte</span><span class="sxs-lookup"><span data-stu-id="42c6f-158">Byte</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="42c6f-159">Columnas</span><span class="sxs-lookup"><span data-stu-id="42c6f-159">Columns</span></span>  
  
|<span data-ttu-id="42c6f-160">ColumName</span><span class="sxs-lookup"><span data-stu-id="42c6f-160">ColumnName</span></span>|<span data-ttu-id="42c6f-161">DataType</span><span class="sxs-lookup"><span data-stu-id="42c6f-161">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="42c6f-162">TABLE_CAT</span><span class="sxs-lookup"><span data-stu-id="42c6f-162">TABLE_CAT</span></span>|<span data-ttu-id="42c6f-163">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-163">String</span></span>|  
|<span data-ttu-id="42c6f-164">TABLE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="42c6f-164">TABLE_SCHEM</span></span>|<span data-ttu-id="42c6f-165">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-165">String</span></span>|  
|<span data-ttu-id="42c6f-166">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-166">TABLE_NAME</span></span>|<span data-ttu-id="42c6f-167">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-167">String</span></span>|  
|<span data-ttu-id="42c6f-168">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-168">COLUMN_NAME</span></span>|<span data-ttu-id="42c6f-169">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-169">String</span></span>|  
|<span data-ttu-id="42c6f-170">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-170">DATA_TYPE</span></span>|<span data-ttu-id="42c6f-171">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-171">Int16</span></span>|  
|<span data-ttu-id="42c6f-172">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-172">TYPE_NAME</span></span>|<span data-ttu-id="42c6f-173">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-173">String</span></span>|  
|<span data-ttu-id="42c6f-174">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="42c6f-174">COLUMN_SIZE</span></span>|<span data-ttu-id="42c6f-175">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-175">Int32</span></span>|  
|<span data-ttu-id="42c6f-176">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="42c6f-176">BUFFER_LENGTH</span></span>|<span data-ttu-id="42c6f-177">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-177">Int32</span></span>|  
|<span data-ttu-id="42c6f-178">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="42c6f-178">DECIMAL_DIGITS</span></span>|<span data-ttu-id="42c6f-179">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-179">Int16</span></span>|  
|<span data-ttu-id="42c6f-180">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="42c6f-180">NUM_PREC_RADIX</span></span>|<span data-ttu-id="42c6f-181">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-181">Int16</span></span>|  
|<span data-ttu-id="42c6f-182">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="42c6f-182">NULLABLE</span></span>|<span data-ttu-id="42c6f-183">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-183">Int16</span></span>|  
|<span data-ttu-id="42c6f-184">REMARKS</span><span class="sxs-lookup"><span data-stu-id="42c6f-184">REMARKS</span></span>|<span data-ttu-id="42c6f-185">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-185">String</span></span>|  
|<span data-ttu-id="42c6f-186">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="42c6f-186">COLUMN_DEF</span></span>|<span data-ttu-id="42c6f-187">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-187">String</span></span>|  
|<span data-ttu-id="42c6f-188">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-188">SQL_DATA_TYPE</span></span>|<span data-ttu-id="42c6f-189">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-189">Int16</span></span>|  
|<span data-ttu-id="42c6f-190">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="42c6f-190">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="42c6f-191">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-191">Int16</span></span>|  
|<span data-ttu-id="42c6f-192">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="42c6f-192">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="42c6f-193">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-193">Int32</span></span>|  
|<span data-ttu-id="42c6f-194">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="42c6f-194">ORDINAL_POSITION</span></span>|<span data-ttu-id="42c6f-195">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-195">Int32</span></span>|  
|<span data-ttu-id="42c6f-196">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="42c6f-196">IS_NULLABLE</span></span>|<span data-ttu-id="42c6f-197">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-197">String</span></span>|  
|<span data-ttu-id="42c6f-198">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="42c6f-198">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="42c6f-199">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-199">String</span></span>|  
|<span data-ttu-id="42c6f-200">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="42c6f-200">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="42c6f-201">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-201">String</span></span>|  
|<span data-ttu-id="42c6f-202">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-202">SS_DATA_TYPE</span></span>|<span data-ttu-id="42c6f-203">Byte</span><span class="sxs-lookup"><span data-stu-id="42c6f-203">Byte</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="42c6f-204">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="42c6f-204">Procedures</span></span>  
  
|<span data-ttu-id="42c6f-205">ColumName</span><span class="sxs-lookup"><span data-stu-id="42c6f-205">ColumnName</span></span>|<span data-ttu-id="42c6f-206">DataType</span><span class="sxs-lookup"><span data-stu-id="42c6f-206">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="42c6f-207">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="42c6f-207">PROCEDURE_CAT</span></span>|<span data-ttu-id="42c6f-208">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-208">String</span></span>|  
|<span data-ttu-id="42c6f-209">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="42c6f-209">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="42c6f-210">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-210">String</span></span>|  
|<span data-ttu-id="42c6f-211">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-211">PROCEDURE_NAME</span></span>|<span data-ttu-id="42c6f-212">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-212">String</span></span>|  
|<span data-ttu-id="42c6f-213">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="42c6f-213">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="42c6f-214">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-214">Int32</span></span>|  
|<span data-ttu-id="42c6f-215">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="42c6f-215">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="42c6f-216">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-216">Int32</span></span>|  
|<span data-ttu-id="42c6f-217">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="42c6f-217">NUM_RESULT_SETS</span></span>|<span data-ttu-id="42c6f-218">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-218">Int32</span></span>|  
|<span data-ttu-id="42c6f-219">REMARKS</span><span class="sxs-lookup"><span data-stu-id="42c6f-219">REMARKS</span></span>|<span data-ttu-id="42c6f-220">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-220">String</span></span>|  
|<span data-ttu-id="42c6f-221">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-221">PROCEDURE_TYPE</span></span>|<span data-ttu-id="42c6f-222">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-222">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="42c6f-223">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="42c6f-223">ProcedureColumns</span></span>  
  
|<span data-ttu-id="42c6f-224">ColumName</span><span class="sxs-lookup"><span data-stu-id="42c6f-224">ColumnName</span></span>|<span data-ttu-id="42c6f-225">DataType</span><span class="sxs-lookup"><span data-stu-id="42c6f-225">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="42c6f-226">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="42c6f-226">PROCEDURE_CAT</span></span>|<span data-ttu-id="42c6f-227">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-227">String</span></span>|  
|<span data-ttu-id="42c6f-228">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="42c6f-228">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="42c6f-229">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-229">String</span></span>|  
|<span data-ttu-id="42c6f-230">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-230">PROCEDURE_NAME</span></span>|<span data-ttu-id="42c6f-231">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-231">String</span></span>|  
|<span data-ttu-id="42c6f-232">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-232">COLUMN_NAME</span></span>|<span data-ttu-id="42c6f-233">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-233">String</span></span>|  
|<span data-ttu-id="42c6f-234">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-234">COLUMN_TYPE</span></span>|<span data-ttu-id="42c6f-235">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-235">Int16</span></span>|  
|<span data-ttu-id="42c6f-236">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-236">DATA_TYPE</span></span>|<span data-ttu-id="42c6f-237">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-237">Int16</span></span>|  
|<span data-ttu-id="42c6f-238">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-238">TYPE_NAME</span></span>|<span data-ttu-id="42c6f-239">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-239">String</span></span>|  
|<span data-ttu-id="42c6f-240">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="42c6f-240">COLUMN_SIZE</span></span>|<span data-ttu-id="42c6f-241">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-241">Int32</span></span>|  
|<span data-ttu-id="42c6f-242">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="42c6f-242">BUFFER_LENGTH</span></span>|<span data-ttu-id="42c6f-243">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-243">Int32</span></span>|  
|<span data-ttu-id="42c6f-244">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="42c6f-244">DECIMAL_DIGITS</span></span>|<span data-ttu-id="42c6f-245">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-245">Int16</span></span>|  
|<span data-ttu-id="42c6f-246">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="42c6f-246">NUM_PREC_RADIX</span></span>|<span data-ttu-id="42c6f-247">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-247">Int16</span></span>|  
|<span data-ttu-id="42c6f-248">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="42c6f-248">NULLABLE</span></span>|<span data-ttu-id="42c6f-249">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-249">Int16</span></span>|  
|<span data-ttu-id="42c6f-250">REMARKS</span><span class="sxs-lookup"><span data-stu-id="42c6f-250">REMARKS</span></span>|<span data-ttu-id="42c6f-251">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-251">String</span></span>|  
|<span data-ttu-id="42c6f-252">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="42c6f-252">COLUMN_DEF</span></span>|<span data-ttu-id="42c6f-253">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-253">String</span></span>|  
|<span data-ttu-id="42c6f-254">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-254">SQL_DATA_TYPE</span></span>|<span data-ttu-id="42c6f-255">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-255">Int16</span></span>|  
|<span data-ttu-id="42c6f-256">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="42c6f-256">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="42c6f-257">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-257">Int16</span></span>|  
|<span data-ttu-id="42c6f-258">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="42c6f-258">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="42c6f-259">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-259">Int32</span></span>|  
|<span data-ttu-id="42c6f-260">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="42c6f-260">ORDINAL_POSITION</span></span>|<span data-ttu-id="42c6f-261">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-261">Int32</span></span>|  
|<span data-ttu-id="42c6f-262">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="42c6f-262">IS_NULLABLE</span></span>|<span data-ttu-id="42c6f-263">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-263">String</span></span>|  
|<span data-ttu-id="42c6f-264">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="42c6f-264">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="42c6f-265">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-265">String</span></span>|  
|<span data-ttu-id="42c6f-266">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="42c6f-266">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="42c6f-267">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-267">String</span></span>|  
|<span data-ttu-id="42c6f-268">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-268">SS_DATA_TYPE</span></span>|<span data-ttu-id="42c6f-269">Byte</span><span class="sxs-lookup"><span data-stu-id="42c6f-269">Byte</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="42c6f-270">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="42c6f-270">ProcedureParameters</span></span>  
  
|<span data-ttu-id="42c6f-271">ColumName</span><span class="sxs-lookup"><span data-stu-id="42c6f-271">ColumnName</span></span>|<span data-ttu-id="42c6f-272">DataType</span><span class="sxs-lookup"><span data-stu-id="42c6f-272">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="42c6f-273">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="42c6f-273">PROCEDURE_CAT</span></span>|<span data-ttu-id="42c6f-274">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-274">String</span></span>|  
|<span data-ttu-id="42c6f-275">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="42c6f-275">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="42c6f-276">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-276">String</span></span>|  
|<span data-ttu-id="42c6f-277">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-277">PROCEDURE_NAME</span></span>|<span data-ttu-id="42c6f-278">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-278">String</span></span>|  
|<span data-ttu-id="42c6f-279">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-279">COLUMN_NAME</span></span>|<span data-ttu-id="42c6f-280">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-280">String</span></span>|  
|<span data-ttu-id="42c6f-281">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-281">COLUMN_TYPE</span></span>|<span data-ttu-id="42c6f-282">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-282">Int16</span></span>|  
|<span data-ttu-id="42c6f-283">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-283">DATA_TYPE</span></span>|<span data-ttu-id="42c6f-284">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-284">Int16</span></span>|  
|<span data-ttu-id="42c6f-285">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-285">TYPE_NAME</span></span>|<span data-ttu-id="42c6f-286">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-286">String</span></span>|  
|<span data-ttu-id="42c6f-287">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="42c6f-287">COLUMN_SIZE</span></span>|<span data-ttu-id="42c6f-288">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-288">Int32</span></span>|  
|<span data-ttu-id="42c6f-289">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="42c6f-289">BUFFER_LENGTH</span></span>|<span data-ttu-id="42c6f-290">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-290">Int32</span></span>|  
|<span data-ttu-id="42c6f-291">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="42c6f-291">DECIMAL_DIGITS</span></span>|<span data-ttu-id="42c6f-292">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-292">Int16</span></span>|  
|<span data-ttu-id="42c6f-293">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="42c6f-293">NUM_PREC_RADIX</span></span>|<span data-ttu-id="42c6f-294">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-294">Int16</span></span>|  
|<span data-ttu-id="42c6f-295">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="42c6f-295">NULLABLE</span></span>|<span data-ttu-id="42c6f-296">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-296">Int16</span></span>|  
|<span data-ttu-id="42c6f-297">REMARKS</span><span class="sxs-lookup"><span data-stu-id="42c6f-297">REMARKS</span></span>|<span data-ttu-id="42c6f-298">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-298">String</span></span>|  
|<span data-ttu-id="42c6f-299">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="42c6f-299">COLUMN_DEF</span></span>|<span data-ttu-id="42c6f-300">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-300">String</span></span>|  
|<span data-ttu-id="42c6f-301">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-301">SQL_DATA_TYPE</span></span>|<span data-ttu-id="42c6f-302">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-302">Int16</span></span>|  
|<span data-ttu-id="42c6f-303">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="42c6f-303">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="42c6f-304">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-304">Int16</span></span>|  
|<span data-ttu-id="42c6f-305">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="42c6f-305">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="42c6f-306">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-306">Int32</span></span>|  
|<span data-ttu-id="42c6f-307">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="42c6f-307">ORDINAL_POSITION</span></span>|<span data-ttu-id="42c6f-308">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-308">Int32</span></span>|  
|<span data-ttu-id="42c6f-309">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="42c6f-309">IS_NULLABLE</span></span>|<span data-ttu-id="42c6f-310">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-310">String</span></span>|  
|<span data-ttu-id="42c6f-311">SS_TYPE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="42c6f-311">SS_TYPE_CATALOG</span></span>|<span data-ttu-id="42c6f-312">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-312">String</span></span>|  
|<span data-ttu-id="42c6f-313">SS_TYPE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="42c6f-313">SS_TYPE_SCHEMA</span></span>|<span data-ttu-id="42c6f-314">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-314">String</span></span>|  
|<span data-ttu-id="42c6f-315">SS_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-315">SS_DATA_TYPE</span></span>|<span data-ttu-id="42c6f-316">Byte</span><span class="sxs-lookup"><span data-stu-id="42c6f-316">Byte</span></span>|  
  
## <a name="microsoft-oracle-odbc-driver"></a><span data-ttu-id="42c6f-317">Controlador ODBC para Oracle de Microsoft</span><span class="sxs-lookup"><span data-stu-id="42c6f-317">Microsoft Oracle ODBC Driver</span></span>  
 <span data-ttu-id="42c6f-318">El controlador ODBC de Oracle de Microsoft SQL Server admite además las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="42c6f-318">The Microsoft SQL Server Oracle ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="42c6f-319">Tablas</span><span class="sxs-lookup"><span data-stu-id="42c6f-319">Tables</span></span>  
  
-   <span data-ttu-id="42c6f-320">Columnas</span><span class="sxs-lookup"><span data-stu-id="42c6f-320">Columns</span></span>  
  
-   <span data-ttu-id="42c6f-321">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="42c6f-321">Procedures</span></span>  
  
-   <span data-ttu-id="42c6f-322">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="42c6f-322">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="42c6f-323">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="42c6f-323">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="42c6f-324">Vistas</span><span class="sxs-lookup"><span data-stu-id="42c6f-324">Views</span></span>  
  
-   <span data-ttu-id="42c6f-325">Índices</span><span class="sxs-lookup"><span data-stu-id="42c6f-325">Indexes</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="42c6f-326">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="42c6f-326">Tables and Views</span></span>  
  
|<span data-ttu-id="42c6f-327">ColumName</span><span class="sxs-lookup"><span data-stu-id="42c6f-327">ColumnName</span></span>|<span data-ttu-id="42c6f-328">DataType</span><span class="sxs-lookup"><span data-stu-id="42c6f-328">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="42c6f-329">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="42c6f-329">TABLE_QUALIFIER</span></span>|<span data-ttu-id="42c6f-330">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-330">String</span></span>|  
|<span data-ttu-id="42c6f-331">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="42c6f-331">TABLE_OWNER</span></span>|<span data-ttu-id="42c6f-332">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-332">String</span></span>|  
|<span data-ttu-id="42c6f-333">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-333">TABLE_NAME</span></span>|<span data-ttu-id="42c6f-334">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-334">String</span></span>|  
|<span data-ttu-id="42c6f-335">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-335">TABLE_TYPE</span></span>|<span data-ttu-id="42c6f-336">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-336">String</span></span>|  
|<span data-ttu-id="42c6f-337">REMARKS</span><span class="sxs-lookup"><span data-stu-id="42c6f-337">REMARKS</span></span>|<span data-ttu-id="42c6f-338">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-338">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="42c6f-339">Columnas</span><span class="sxs-lookup"><span data-stu-id="42c6f-339">Columns</span></span>  
  
|<span data-ttu-id="42c6f-340">ColumName</span><span class="sxs-lookup"><span data-stu-id="42c6f-340">ColumnName</span></span>|<span data-ttu-id="42c6f-341">DataType</span><span class="sxs-lookup"><span data-stu-id="42c6f-341">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="42c6f-342">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="42c6f-342">TABLE_QUALIFIER</span></span>|<span data-ttu-id="42c6f-343">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-343">String</span></span>|  
|<span data-ttu-id="42c6f-344">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="42c6f-344">TABLE_OWNER</span></span>|<span data-ttu-id="42c6f-345">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-345">String</span></span>|  
|<span data-ttu-id="42c6f-346">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-346">TABLE_NAME</span></span>|<span data-ttu-id="42c6f-347">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-347">String</span></span>|  
|<span data-ttu-id="42c6f-348">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-348">COLUMN_NAME</span></span>|<span data-ttu-id="42c6f-349">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-349">String</span></span>|  
|<span data-ttu-id="42c6f-350">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-350">DATA_TYPE</span></span>|<span data-ttu-id="42c6f-351">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-351">Int16</span></span>|  
|<span data-ttu-id="42c6f-352">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-352">TYPE_NAME</span></span>|<span data-ttu-id="42c6f-353">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-353">String</span></span>|  
|<span data-ttu-id="42c6f-354">PRECISION</span><span class="sxs-lookup"><span data-stu-id="42c6f-354">PRECISION</span></span>|<span data-ttu-id="42c6f-355">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-355">Int32</span></span>|  
|<span data-ttu-id="42c6f-356">LENGTH</span><span class="sxs-lookup"><span data-stu-id="42c6f-356">LENGTH</span></span>|<span data-ttu-id="42c6f-357">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-357">Int32</span></span>|  
|<span data-ttu-id="42c6f-358">SCALE</span><span class="sxs-lookup"><span data-stu-id="42c6f-358">SCALE</span></span>|<span data-ttu-id="42c6f-359">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-359">Int16</span></span>|  
|<span data-ttu-id="42c6f-360">RADIX</span><span class="sxs-lookup"><span data-stu-id="42c6f-360">RADIX</span></span>|<span data-ttu-id="42c6f-361">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-361">Int16</span></span>|  
|<span data-ttu-id="42c6f-362">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="42c6f-362">NULLABLE</span></span>|<span data-ttu-id="42c6f-363">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-363">Int16</span></span>|  
|<span data-ttu-id="42c6f-364">REMARKS</span><span class="sxs-lookup"><span data-stu-id="42c6f-364">REMARKS</span></span>|<span data-ttu-id="42c6f-365">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-365">String</span></span>|  
|<span data-ttu-id="42c6f-366">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="42c6f-366">ORDINAL_POSITION</span></span>|<span data-ttu-id="42c6f-367">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-367">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="42c6f-368">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="42c6f-368">Procedures</span></span>  
  
|<span data-ttu-id="42c6f-369">ColumName</span><span class="sxs-lookup"><span data-stu-id="42c6f-369">ColumnName</span></span>|<span data-ttu-id="42c6f-370">DataType</span><span class="sxs-lookup"><span data-stu-id="42c6f-370">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="42c6f-371">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="42c6f-371">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="42c6f-372">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-372">String</span></span>|  
|<span data-ttu-id="42c6f-373">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="42c6f-373">PROCEDURE_OWNER</span></span>|<span data-ttu-id="42c6f-374">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-374">String</span></span>|  
|<span data-ttu-id="42c6f-375">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-375">PROCEDURE_NAME</span></span>|<span data-ttu-id="42c6f-376">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-376">String</span></span>|  
|<span data-ttu-id="42c6f-377">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="42c6f-377">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="42c6f-378">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-378">Int16</span></span>|  
|<span data-ttu-id="42c6f-379">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="42c6f-379">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="42c6f-380">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-380">Int16</span></span>|  
|<span data-ttu-id="42c6f-381">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="42c6f-381">NUM_RESULT_SETS</span></span>|<span data-ttu-id="42c6f-382">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-382">Int16</span></span>|  
|<span data-ttu-id="42c6f-383">REMARKS</span><span class="sxs-lookup"><span data-stu-id="42c6f-383">REMARKS</span></span>|<span data-ttu-id="42c6f-384">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-384">String</span></span>|  
|<span data-ttu-id="42c6f-385">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-385">PROCEDURE_TYPE</span></span>|<span data-ttu-id="42c6f-386">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-386">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="42c6f-387">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="42c6f-387">ProcedureColumns</span></span>  
  
|<span data-ttu-id="42c6f-388">ColumName</span><span class="sxs-lookup"><span data-stu-id="42c6f-388">ColumnName</span></span>|<span data-ttu-id="42c6f-389">DataType</span><span class="sxs-lookup"><span data-stu-id="42c6f-389">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="42c6f-390">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="42c6f-390">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="42c6f-391">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-391">String</span></span>|  
|<span data-ttu-id="42c6f-392">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="42c6f-392">PROCEDURE_OWNER</span></span>|<span data-ttu-id="42c6f-393">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-393">String</span></span>|  
|<span data-ttu-id="42c6f-394">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-394">PROCEDURE_NAME</span></span>|<span data-ttu-id="42c6f-395">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-395">String</span></span>|  
|<span data-ttu-id="42c6f-396">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-396">COLUMN_NAME</span></span>|<span data-ttu-id="42c6f-397">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-397">String</span></span>|  
|<span data-ttu-id="42c6f-398">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-398">COLUMN_TYPE</span></span>|<span data-ttu-id="42c6f-399">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-399">Int16</span></span>|  
|<span data-ttu-id="42c6f-400">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-400">DATA_TYPE</span></span>|<span data-ttu-id="42c6f-401">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-401">Int16</span></span>|  
|<span data-ttu-id="42c6f-402">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-402">TYPE_NAME</span></span>|<span data-ttu-id="42c6f-403">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-403">String</span></span>|  
|<span data-ttu-id="42c6f-404">PRECISION</span><span class="sxs-lookup"><span data-stu-id="42c6f-404">PRECISION</span></span>|<span data-ttu-id="42c6f-405">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-405">Int32</span></span>|  
|<span data-ttu-id="42c6f-406">LENGTH</span><span class="sxs-lookup"><span data-stu-id="42c6f-406">LENGTH</span></span>|<span data-ttu-id="42c6f-407">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-407">Int32</span></span>|  
|<span data-ttu-id="42c6f-408">SCALE</span><span class="sxs-lookup"><span data-stu-id="42c6f-408">SCALE</span></span>|<span data-ttu-id="42c6f-409">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-409">Int16</span></span>|  
|<span data-ttu-id="42c6f-410">RADIX</span><span class="sxs-lookup"><span data-stu-id="42c6f-410">RADIX</span></span>|<span data-ttu-id="42c6f-411">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-411">Int16</span></span>|  
|<span data-ttu-id="42c6f-412">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="42c6f-412">NULLABLE</span></span>|<span data-ttu-id="42c6f-413">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-413">Int16</span></span>|  
|<span data-ttu-id="42c6f-414">REMARKS</span><span class="sxs-lookup"><span data-stu-id="42c6f-414">REMARKS</span></span>|<span data-ttu-id="42c6f-415">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-415">String</span></span>|  
|<span data-ttu-id="42c6f-416">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="42c6f-416">OVERLOAD</span></span>|<span data-ttu-id="42c6f-417">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-417">Int32</span></span>|  
|<span data-ttu-id="42c6f-418">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="42c6f-418">ORDINAL_POSITION</span></span>|<span data-ttu-id="42c6f-419">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-419">Int32</span></span>|  
  
## <a name="microsoft-jet-odbc-driver"></a><span data-ttu-id="42c6f-420">Controlador ODBC de Microsoft para Jet</span><span class="sxs-lookup"><span data-stu-id="42c6f-420">Microsoft Jet ODBC Driver</span></span>  
 <span data-ttu-id="42c6f-421">El controlador ODBC de Microsoft para Jet admite, además de las colecciones de esquemas comunes, las siguientes colecciones de esquemas específicas:</span><span class="sxs-lookup"><span data-stu-id="42c6f-421">The Microsoft Jet ODBC Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="42c6f-422">Tablas</span><span class="sxs-lookup"><span data-stu-id="42c6f-422">Tables</span></span>  
  
-   <span data-ttu-id="42c6f-423">Índices</span><span class="sxs-lookup"><span data-stu-id="42c6f-423">Indexes</span></span>  
  
-   <span data-ttu-id="42c6f-424">Columnas</span><span class="sxs-lookup"><span data-stu-id="42c6f-424">Columns</span></span>  
  
-   <span data-ttu-id="42c6f-425">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="42c6f-425">Procedures</span></span>  
  
-   <span data-ttu-id="42c6f-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="42c6f-426">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="42c6f-427">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="42c6f-427">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="42c6f-428">Vistas</span><span class="sxs-lookup"><span data-stu-id="42c6f-428">Views</span></span>  
  
### <a name="tables-and-views"></a><span data-ttu-id="42c6f-429">Tablas y vistas</span><span class="sxs-lookup"><span data-stu-id="42c6f-429">Tables and Views</span></span>  
  
|<span data-ttu-id="42c6f-430">ColumName</span><span class="sxs-lookup"><span data-stu-id="42c6f-430">ColumnName</span></span>|<span data-ttu-id="42c6f-431">DataType</span><span class="sxs-lookup"><span data-stu-id="42c6f-431">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="42c6f-432">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="42c6f-432">TABLE_QUALIFIER</span></span>|<span data-ttu-id="42c6f-433">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-433">String</span></span>|  
|<span data-ttu-id="42c6f-434">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="42c6f-434">TABLE_OWNER</span></span>|<span data-ttu-id="42c6f-435">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-435">String</span></span>|  
|<span data-ttu-id="42c6f-436">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-436">TABLE_NAME</span></span>|<span data-ttu-id="42c6f-437">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-437">String</span></span>|  
|<span data-ttu-id="42c6f-438">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-438">TABLE_TYPE</span></span>|<span data-ttu-id="42c6f-439">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-439">String</span></span>|  
|<span data-ttu-id="42c6f-440">REMARKS</span><span class="sxs-lookup"><span data-stu-id="42c6f-440">REMARKS</span></span>|<span data-ttu-id="42c6f-441">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-441">String</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="42c6f-442">Columnas</span><span class="sxs-lookup"><span data-stu-id="42c6f-442">Columns</span></span>  
  
|<span data-ttu-id="42c6f-443">ColumName</span><span class="sxs-lookup"><span data-stu-id="42c6f-443">ColumnName</span></span>|<span data-ttu-id="42c6f-444">DataType</span><span class="sxs-lookup"><span data-stu-id="42c6f-444">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="42c6f-445">TABLE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="42c6f-445">TABLE_QUALIFIER</span></span>|<span data-ttu-id="42c6f-446">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-446">String</span></span>|  
|<span data-ttu-id="42c6f-447">TABLE_OWNER</span><span class="sxs-lookup"><span data-stu-id="42c6f-447">TABLE_OWNER</span></span>|<span data-ttu-id="42c6f-448">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-448">String</span></span>|  
|<span data-ttu-id="42c6f-449">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-449">TABLE_NAME</span></span>|<span data-ttu-id="42c6f-450">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-450">String</span></span>|  
|<span data-ttu-id="42c6f-451">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-451">COLUMN_NAME</span></span>|<span data-ttu-id="42c6f-452">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-452">String</span></span>|  
|<span data-ttu-id="42c6f-453">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-453">DATA_TYPE</span></span>|<span data-ttu-id="42c6f-454">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-454">Int16</span></span>|  
|<span data-ttu-id="42c6f-455">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-455">TYPE_NAME</span></span>|<span data-ttu-id="42c6f-456">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-456">String</span></span>|  
|<span data-ttu-id="42c6f-457">PRECISION</span><span class="sxs-lookup"><span data-stu-id="42c6f-457">PRECISION</span></span>|<span data-ttu-id="42c6f-458">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-458">Int32</span></span>|  
|<span data-ttu-id="42c6f-459">LENGTH</span><span class="sxs-lookup"><span data-stu-id="42c6f-459">LENGTH</span></span>|<span data-ttu-id="42c6f-460">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-460">Int32</span></span>|  
|<span data-ttu-id="42c6f-461">SCALE</span><span class="sxs-lookup"><span data-stu-id="42c6f-461">SCALE</span></span>|<span data-ttu-id="42c6f-462">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-462">Int16</span></span>|  
|<span data-ttu-id="42c6f-463">RADIX</span><span class="sxs-lookup"><span data-stu-id="42c6f-463">RADIX</span></span>|<span data-ttu-id="42c6f-464">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-464">Int16</span></span>|  
|<span data-ttu-id="42c6f-465">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="42c6f-465">NULLABLE</span></span>|<span data-ttu-id="42c6f-466">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-466">Int16</span></span>|  
|<span data-ttu-id="42c6f-467">REMARKS</span><span class="sxs-lookup"><span data-stu-id="42c6f-467">REMARKS</span></span>|<span data-ttu-id="42c6f-468">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-468">String</span></span>|  
|<span data-ttu-id="42c6f-469">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="42c6f-469">ORDINAL_POSITION</span></span>|<span data-ttu-id="42c6f-470">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-470">Int32</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="42c6f-471">Procedimientos</span><span class="sxs-lookup"><span data-stu-id="42c6f-471">Procedures</span></span>  
  
|<span data-ttu-id="42c6f-472">ColumName</span><span class="sxs-lookup"><span data-stu-id="42c6f-472">ColumnName</span></span>|<span data-ttu-id="42c6f-473">DataType</span><span class="sxs-lookup"><span data-stu-id="42c6f-473">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="42c6f-474">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="42c6f-474">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="42c6f-475">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-475">String</span></span>|  
|<span data-ttu-id="42c6f-476">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="42c6f-476">PROCEDURE_OWNER</span></span>|<span data-ttu-id="42c6f-477">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-477">String</span></span>|  
|<span data-ttu-id="42c6f-478">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-478">PROCEDURE_NAME</span></span>|<span data-ttu-id="42c6f-479">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-479">String</span></span>|  
|<span data-ttu-id="42c6f-480">NUM_INPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="42c6f-480">NUM_INPUT_PARAMS</span></span>|<span data-ttu-id="42c6f-481">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-481">Int16</span></span>|  
|<span data-ttu-id="42c6f-482">NUM_OUTPUT_PARAMS</span><span class="sxs-lookup"><span data-stu-id="42c6f-482">NUM_OUTPUT_PARAMS</span></span>|<span data-ttu-id="42c6f-483">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-483">Int16</span></span>|  
|<span data-ttu-id="42c6f-484">NUM_RESULT_SETS</span><span class="sxs-lookup"><span data-stu-id="42c6f-484">NUM_RESULT_SETS</span></span>|<span data-ttu-id="42c6f-485">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-485">Int16</span></span>|  
|<span data-ttu-id="42c6f-486">REMARKS</span><span class="sxs-lookup"><span data-stu-id="42c6f-486">REMARKS</span></span>|<span data-ttu-id="42c6f-487">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-487">String</span></span>|  
|<span data-ttu-id="42c6f-488">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-488">PROCEDURE_TYPE</span></span>|<span data-ttu-id="42c6f-489">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-489">Int16</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="42c6f-490">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="42c6f-490">ProcedureColumns</span></span>  
  
|<span data-ttu-id="42c6f-491">ColumName</span><span class="sxs-lookup"><span data-stu-id="42c6f-491">ColumnName</span></span>|<span data-ttu-id="42c6f-492">DataType</span><span class="sxs-lookup"><span data-stu-id="42c6f-492">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="42c6f-493">PROCEDURE_QUALIFIER</span><span class="sxs-lookup"><span data-stu-id="42c6f-493">PROCEDURE_QUALIFIER</span></span>|<span data-ttu-id="42c6f-494">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-494">String</span></span>|  
|<span data-ttu-id="42c6f-495">PROCEDURE_OWNER</span><span class="sxs-lookup"><span data-stu-id="42c6f-495">PROCEDURE_OWNER</span></span>|<span data-ttu-id="42c6f-496">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-496">String</span></span>|  
|<span data-ttu-id="42c6f-497">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-497">PROCEDURE_NAME</span></span>|<span data-ttu-id="42c6f-498">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-498">String</span></span>|  
|<span data-ttu-id="42c6f-499">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-499">COLUMN_NAME</span></span>|<span data-ttu-id="42c6f-500">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-500">String</span></span>|  
|<span data-ttu-id="42c6f-501">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-501">COLUMN_TYPE</span></span>|<span data-ttu-id="42c6f-502">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-502">Int16</span></span>|  
|<span data-ttu-id="42c6f-503">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-503">DATA_TYPE</span></span>|<span data-ttu-id="42c6f-504">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-504">Int16</span></span>|  
|<span data-ttu-id="42c6f-505">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-505">TYPE_NAME</span></span>|<span data-ttu-id="42c6f-506">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-506">String</span></span>|  
|<span data-ttu-id="42c6f-507">PRECISION</span><span class="sxs-lookup"><span data-stu-id="42c6f-507">PRECISION</span></span>|<span data-ttu-id="42c6f-508">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-508">Int32</span></span>|  
|<span data-ttu-id="42c6f-509">LENGTH</span><span class="sxs-lookup"><span data-stu-id="42c6f-509">LENGTH</span></span>|<span data-ttu-id="42c6f-510">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-510">Int32</span></span>|  
|<span data-ttu-id="42c6f-511">SCALE</span><span class="sxs-lookup"><span data-stu-id="42c6f-511">SCALE</span></span>|<span data-ttu-id="42c6f-512">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-512">Int16</span></span>|  
|<span data-ttu-id="42c6f-513">RADIX</span><span class="sxs-lookup"><span data-stu-id="42c6f-513">RADIX</span></span>|<span data-ttu-id="42c6f-514">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-514">Int16</span></span>|  
|<span data-ttu-id="42c6f-515">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="42c6f-515">NULLABLE</span></span>|<span data-ttu-id="42c6f-516">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-516">Int16</span></span>|  
|<span data-ttu-id="42c6f-517">REMARKS</span><span class="sxs-lookup"><span data-stu-id="42c6f-517">REMARKS</span></span>|<span data-ttu-id="42c6f-518">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-518">String</span></span>|  
|<span data-ttu-id="42c6f-519">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="42c6f-519">OVERLOAD</span></span>|<span data-ttu-id="42c6f-520">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-520">Int32</span></span>|  
|<span data-ttu-id="42c6f-521">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="42c6f-521">ORDINAL_POSITION</span></span>|<span data-ttu-id="42c6f-522">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-522">Int32</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="42c6f-523">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="42c6f-523">ProcedureParameters</span></span>  
  
|<span data-ttu-id="42c6f-524">ColumName</span><span class="sxs-lookup"><span data-stu-id="42c6f-524">ColumnName</span></span>|<span data-ttu-id="42c6f-525">DataType</span><span class="sxs-lookup"><span data-stu-id="42c6f-525">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="42c6f-526">PROCEDURE_CAT</span><span class="sxs-lookup"><span data-stu-id="42c6f-526">PROCEDURE_CAT</span></span>|<span data-ttu-id="42c6f-527">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-527">String</span></span>|  
|<span data-ttu-id="42c6f-528">PROCEDURE_SCHEM</span><span class="sxs-lookup"><span data-stu-id="42c6f-528">PROCEDURE_SCHEM</span></span>|<span data-ttu-id="42c6f-529">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-529">String</span></span>|  
|<span data-ttu-id="42c6f-530">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-530">PROCEDURE_NAME</span></span>|<span data-ttu-id="42c6f-531">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-531">String</span></span>|  
|<span data-ttu-id="42c6f-532">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-532">COLUMN_NAME</span></span>|<span data-ttu-id="42c6f-533">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-533">String</span></span>|  
|<span data-ttu-id="42c6f-534">COLUMN_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-534">COLUMN_TYPE</span></span>|<span data-ttu-id="42c6f-535">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-535">Int16</span></span>|  
|<span data-ttu-id="42c6f-536">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-536">DATA_TYPE</span></span>|<span data-ttu-id="42c6f-537">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-537">Int16</span></span>|  
|<span data-ttu-id="42c6f-538">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="42c6f-538">TYPE_NAME</span></span>|<span data-ttu-id="42c6f-539">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-539">String</span></span>|  
|<span data-ttu-id="42c6f-540">COLUMN_SIZE</span><span class="sxs-lookup"><span data-stu-id="42c6f-540">COLUMN_SIZE</span></span>|<span data-ttu-id="42c6f-541">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-541">Int32</span></span>|  
|<span data-ttu-id="42c6f-542">BUFFER_LENGTH</span><span class="sxs-lookup"><span data-stu-id="42c6f-542">BUFFER_LENGTH</span></span>|<span data-ttu-id="42c6f-543">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-543">Int32</span></span>|  
|<span data-ttu-id="42c6f-544">DECIMAL_DIGITS</span><span class="sxs-lookup"><span data-stu-id="42c6f-544">DECIMAL_DIGITS</span></span>|<span data-ttu-id="42c6f-545">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-545">Int16</span></span>|  
|<span data-ttu-id="42c6f-546">NUM_PREC_RADIX</span><span class="sxs-lookup"><span data-stu-id="42c6f-546">NUM_PREC_RADIX</span></span>|<span data-ttu-id="42c6f-547">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-547">Int16</span></span>|  
|<span data-ttu-id="42c6f-548">NULLABLE</span><span class="sxs-lookup"><span data-stu-id="42c6f-548">NULLABLE</span></span>|<span data-ttu-id="42c6f-549">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-549">Int16</span></span>|  
|<span data-ttu-id="42c6f-550">REMARKS</span><span class="sxs-lookup"><span data-stu-id="42c6f-550">REMARKS</span></span>|<span data-ttu-id="42c6f-551">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-551">String</span></span>|  
|<span data-ttu-id="42c6f-552">COLUMN_DEF</span><span class="sxs-lookup"><span data-stu-id="42c6f-552">COLUMN_DEF</span></span>|<span data-ttu-id="42c6f-553">String</span><span class="sxs-lookup"><span data-stu-id="42c6f-553">String</span></span>|  
|<span data-ttu-id="42c6f-554">SQL_DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="42c6f-554">SQL_DATA_TYPE</span></span>|<span data-ttu-id="42c6f-555">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-555">Int16</span></span>|  
|<span data-ttu-id="42c6f-556">SQL_DATETIME_SUB</span><span class="sxs-lookup"><span data-stu-id="42c6f-556">SQL_DATETIME_SUB</span></span>|<span data-ttu-id="42c6f-557">Int16</span><span class="sxs-lookup"><span data-stu-id="42c6f-557">Int16</span></span>|  
|<span data-ttu-id="42c6f-558">CHAR_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="42c6f-558">CHAR_OCTET_LENGTH</span></span>|<span data-ttu-id="42c6f-559">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-559">Int32</span></span>|  
|<span data-ttu-id="42c6f-560">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="42c6f-560">ORDINAL_POSITION</span></span>|<span data-ttu-id="42c6f-561">Int32</span><span class="sxs-lookup"><span data-stu-id="42c6f-561">Int32</span></span>|  
|<span data-ttu-id="42c6f-562">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="42c6f-562">IS_NULLABLE</span></span>|<span data-ttu-id="42c6f-563">Cadena</span><span class="sxs-lookup"><span data-stu-id="42c6f-563">String</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="42c6f-564">Vea también</span><span class="sxs-lookup"><span data-stu-id="42c6f-564">See Also</span></span>  
 [<span data-ttu-id="42c6f-565">Proveedores administrados de ADO.NET y Centro para desarrolladores de DataSet</span><span class="sxs-lookup"><span data-stu-id="42c6f-565">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
