---
title: Advanced eDiscovery에서 지원되는 파일 형식
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 Advanced eDiscovery에서 지원되는 파일 형식 목록(Advanced eDiscovery의 OCR 기능에서 지원하는 이미지 파일 형식 포함)
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a552e6cf0d32e77c2a21bc959ae313e6fc53d4eb
ms.sourcegitcommit: 9f5b136b96b3af4db4cc6f5b1f35130ae60d6b12
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "47817131"
---
# <a name="supported-file-types-in-advanced-ediscovery"></a>Advanced eDiscovery에서 지원되는 파일 형식

Advanced eDiscovery는 다양한 수준에서 많은 파일 형식을 지원합니다. 지원 파일 형식은 이 문서의 다음 표에 설명되어 있습니다. 이 목록은 마무리되지 않은 것으로, 유효성 검사 테스트를 계속할 때 새 파일 형식을 추가할 것입니다. 다음 표에서는 텍스트 추출(이미지 파일에 대한 광학 문자 인식 또는 OCR 텍스트 추출)에 대해 파일 형식이 지원되는지, 기본 뷰어에서 볼 수 있으며, Advanced eDiscovery의 Annotate 뷰어에서도 지원될지 나타냅니다.

## <a name="archive--container"></a>보관/컨테이너

| Mime 형식 | 파일 식별 | 메타데이터 추출 | 컨테이너 추출 | 가능한 확장 |
|:---- |:---- |:---- |:---- |:---- |
|application/x-7z-compressed | 예 | 예 | 예 | .7z |
|application/x-rar-compressed | 예 | 예 | 예 | .rar |
|application/x-tar | 예 | 예 | 예 | .tar |
|application/zip | 예 | 예 | 예 | .zip |
||||||||

## <a name="audio--video"></a>오디오/비디오

| Mime 형식 | 파일 식별 | 메타데이터 추출 | 텍스트 추출 | 기본 뷰어 | 뷰어 주석 추가 | 가능한 확장 |
|:------| :------| :------| :------| :------| :------| :------|
| application/mp4 | 예 | 예 | 아니요 | 예 | 아니요 | .f4v; .m4a; .m4v; .mp4; .mp4v; .mpeg; .mpeg4 |
|audio/mpeg | 예 | 예 | 아니요 | 예 | 아니요 | .mpeg |
|video/3gpp | 예 | 예 | 아니요 | 예 | 아니요 | .3gp |
|video/3gpp2 | 예 | 예 | 아니요 | 예 | 아니요 | .3g2; .3gp2 |
|video/quicktime | 예 | 예 | 아니요 | 예 | 아니요 | .moov; .mov; .qt |
|video/x-m4v | 예 | 예 | 아니요 | 예 | 아니요 | .m4v |
||||||||

## <a name="database"></a>Database

| Mime 형식 | 파일 식별 | 메타데이터 추출 | 텍스트 추출 | 기본 뷰어 | 뷰어 주석 추가 | 가능한 확장 |
|:------| :------| :------| :------| :------| :------| :------|
|application/x-msaccess | 예 | 예 | 예 | 아니요 | 아니요 | .mdb |
||||||||

## <a name="email"></a>전자 메일

|Mime 형식 |파일 식별 |메타데이터 추출 |텍스트 추출 |기본 뷰어 |뷰어 주석 추가 | 가능한 확장 |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-outlook | 예 | 예 | 예 | 예 | 예 | .msg |
|message/rfc822 | 예 | 예 | 예 | 예 | 예 | .eml |
|text/vcard-contact | 예 | 예 | 예 | 예 | 예 | .vcf |
||||||||

## <a name="email-container"></a>전자 메일 컨테이너

| Mime 형식 | 파일 식별 | 메타데이터 추출 | 컨테이너 추출 | 가능한 확장 |
|:------| :------| :------| :------| :------|
|application/mbox | 예 | 예 | 예 | .mbox |
|application/vnd.ms-outlook-pst | 예 | 예 | 예 | .pst |
||||||||

## <a name="html"></a>HTML

| Mime 형식 | 파일 식별 | 메타데이터 추출 | 텍스트 추출 | 기본 뷰어 | 뷰어 주석 추가 | 가능한 확장 |
|:------| :------| :------| :------| :------| :------| :------|
|application/xhtml+xml | 예 | 예 | 예 | 예 | 예 | .xhtml |
|application/xml | 예 | 예 | 예 | 예 | 예 | .xml |
|text/html | 예 | 예 | 예 | 예 | 예 | .htm; .html; .shtml |
||||||||

## <a name="image"></a>이미지

|Mime 형식 |파일 식별 |메타데이터 추출 |OCR 텍스트 추출 |기본 뷰어 |뷰어 주석 추가 |가능한 확장 |
|:------| :------| :------| :------| :------| :------| :------|
|image/bmp | 예 | 예 | 예 | 예 | 예 | .bmp |
|image/emf | 예 | 예 | 예 | 예 | 예 | .emf |
|image/gif | 예 | 예 | 예 | 예 | 예 | .gif |
|image/jpeg | 예 | 예 | 예 | 예 | 예 | .jpeg; .jpg |
|image/png | 예 | 예 | 예 | 예 | 예 | .png |
|image/svg+xml | 예 | 예 | 예 | 예 | 아니요 | .svg |
|image/tiff | 예 | 예 | 예 | 예 | 예 | .tif |
|image/vnd.dwg | 예 | 예 | 예 | 예 | 예 | .dwg; .dxf |
|image/wmf | 예 | 예 | 예 | 예 | 예 | .wmf |
||||||||

## <a name="microsoft-excel"></a>Microsoft Excel

| Mime 형식 | 파일 식별 | 메타데이터 추출 | 텍스트 추출 | 기본 뷰어 | 뷰어 주석 추가 | 가능한 확장 |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-excel | 예 | 예 | 예 | 예 | 예 | .dat; .xls |
|application/vnd.ms-excel.sheet.binary.macroenabled.12 | 예 | 예 | 예 | 예 | 아니요 | .xlsb |
|application/vnd.ms-excel.sheet.macroenabled.12 | 예 | 예 | 예 | 예 | 예 | .xlsm |
|application/vnd.ms-excel.template.macroenabled.12 | 예 | 예 | 예 | 아니요 | 아니요 | .xltm |
|application/vnd.openxmlformats-officedocument.spreadsheetml.sheet | 예 | 예 | 예 | 예 | 예 | .xlsx |
|application/vnd.openxmlformats-officedocument.spreadsheetml.template | 예 | 예 | 예 | 예 | 예 | .xltx |
||||||||

## <a name="microsoft-onenote"></a>Microsoft OneNote

| Mime 형식 | 파일 식별 | 메타데이터 추출 | 텍스트 추출 | 기본 뷰어 | 뷰어 주석 추가 | 가능한 확장 |
|:------| :------| :------| :------| :------| :------| :------|
|application/onenote | 예 | 예 | 예 | 예 | 아니요 | .one |
||||||||

## <a name="microsoft-powerpoint"></a>Microsoft PowerPoint

| Mime 형식 | 파일 식별 | 메타데이터 추출 | 텍스트 추출 | 기본 뷰어 | 뷰어 주석 추가 | 가능한 확장 |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-powerpoint | 예 | 예 | 예 | 예 | 예 | .pot; .pps; .ppt |
|application/vnd.openxmlformats-officedocument.presentationml.presentation | 예 | 예 | 예 | 예 | 예 | .pptx |
|application/vnd.openxmlformats-officedocument.presentationml.slideshow | 예 | 예 | 예 | 예 | 예 | .ppsx |
|application/vnd.openxmlformats-officedocument.presentationml.template | 예 | 예 | 예 | 예 | 예 | .potx |
||||||||

## <a name="microsoft-project"></a>Microsoft Project

| Mime 형식 | 파일 식별 | 메타데이터 추출 | 텍스트 추출 | 기본 뷰어 | 뷰어 주석 추가 | 가능한 확장 |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-project | 예 | 예 | 예 | 아니요 | 예 | .mpp |
||||||||

## <a name="microsoft-publisher"></a>Microsoft Publisher

|Mime 형식 | 파일 식별 | 메타데이터 추출 | 텍스트 추출 | 기본 뷰어 | 뷰어 주석 추가 | 가능한 확장 |
|:------| :------| :------| :------| :------| :------| :------|
|application/x-mspublisher | 예 | 예 | 예 | 예 | 예 | .pub |
||||||||

## <a name="microsoft-visio"></a>Microsoft Visio

| Mime 형식 | 파일 식별 | 메타데이터 추출 | 텍스트 추출 | 기본 뷰어 | 뷰어 주석 추가 | 가능한 확장 |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-visio.drawing | 예 | 예 | 예 | 예 | 아니요 |  |
|application/vnd.visio | 예 | 예 | 예 | 예 | 예 | .vsd |
||||||||

## <a name="microsoft-word"></a>Microsoft Word

| Mime 형식 | 파일 식별 | 메타데이터 추출 | 텍스트 추출 | 기본 뷰어 | 뷰어 주석 추가 | 가능한 확장 |
|:------| :------| :------| :------| :------| :------| :------|
|application/msword | 예 | 예 | 예 | 예 | 예 | .dat; .doc |
| application/rtf | 예 | 예 | 예 | 예 | 예 | .doc; .rtf |
|application/vnd.ms-word.document.macroenabled.12 | 예 | 예 | 예 | 예 | 예 | .docm |
|application/vnd.ms-word.template.macroenabled.12 | 예 | 예 | 예 | 예 | 예 | .dotm |
|application/vnd.openxmlformats-officedocument.wordprocessingml.document | 예 | 예 | 예 | 예 | 예 | .docx |
|application/vnd.openxmlformats-officedocument.wordprocessingml.template | 예 | 예 | 예 | 예 | 예 | .dotx |
||||||||

## <a name="microsoft-works"></a>Microsoft Works

| Mime 형식 | 파일 식별 | 메타데이터 추출 | 텍스트 추출 | 기본 뷰어 | 뷰어 주석 추가 | 가능한 확장 |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.ms-works-ss | 예 | 예 | 아니요 | 아니요 | 아니요 | .wps |
|application/vnd.ms-works-wp | 예 | 예 | 아니요 | 아니요 | 아니요 | .wps |
||||||||

## <a name="open-document-format"></a>문서 형식 열기

| Mime 형식 | 파일 식별 | 메타데이터 추출 | 텍스트 추출 | 기본 뷰어 | 뷰어 주석 추가 | 가능한 확장 |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.oasis.opendocument.text | 예 | 예 | 예 | 예 | 예 | .odt |
||||||||

## <a name="other"></a>기타

| Mime 형식 | 파일 식별 | 메타데이터 추출 | 텍스트 추출 | 기본 뷰어 | 뷰어 주석 추가 | 가능한 확장 |
|:------| :------| :------| :------| :------| :------| :------|
|application/json | 예 | 예 | 예 | 예 | 예 | 해당 없음 |
|application/vnd.ms-graph | 예 | 예 | 아니요 | 아니요 | 아니요 |  |
|application/winhlp | 예 | 예 | 아니요 | 아니요 | 아니요 | .hlp |
|application/x-tnef | 예 | 예 | 아니요 | 아니요 | 아니요 |  |
||||||||

## <a name="plain-text"></a>일반 텍스트

| Mime 형식 | 파일 식별 | 메타데이터 추출 | 텍스트 추출 | 기본 뷰어 | 뷰어 주석 추가 | 가능한 확장 |
|:------| :------| :------| :------| :------| :------| :------|
|text/csv | 예 | 예 | 예 | 예 | 예 | .csv |
|text/plain | 예 | 예 | 예 | 예 | 예 | .con; .css; .csv; .dat; .pl; .txt |
||||||||

## <a name="portable-document-format"></a>PDF(Portable Document Format)

| Mime 형식 | 파일 식별 | 메타데이터 추출 | 텍스트 추출 | 기본 뷰어 | 뷰어 주석 추가 | 가능한 확장 |
|:------| :------| :------| :------| :------| :------| :------|
|application/pdf | 예 | 예 | 예 | 예 | 예 | .pdf |
||||||||

## <a name="word-perfect"></a>완벽한 단어

| Mime 형식 | 파일 식별 | 메타데이터 추출 | 텍스트 추출 | 기본 뷰어 | 뷰어 주석 추가 | 가능한 확장 |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.wordperfect; version=5.0 | 예 | 예 | 예 | 아니요 | 아니요 | .wpd |
|application/vnd.wordperfect; version=5.1 | 예 | 예 | 예 | 아니요 | 아니요 | .wpd |
|application/vnd.wordperfect; version=6.x | 예 | 예 | 예 | 아니요 | 아니요 | .wpd |
||||||||

## <a name="word-pro"></a>Word Pro

| Mime 형식 | 파일 식별 | 메타데이터 추출 | 텍스트 추출 | 기본 뷰어 | 뷰어 주석 추가 | 가능한 확장 |
|:------| :------| :------| :------| :------| :------| :------|
|application/vnd.lotus-wordpro | 예 | 예 | 아니요 | 아니요 | 아니요 | .lwp |
||||||||
