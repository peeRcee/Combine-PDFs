#This program combines separate pdf files into a single pdf file.

#! /usr/bin/python3
# combinePDFappl.py – Combines all the PDFs in the current working directory into a single PDF.

import PyPDF2

pdf1File = open('CLwppi1Mar19.pdf', 'rb')
pdf2File = open('CVwppi1Mar19.pdf', 'rb')
pdf3File = open('Pierre Camp_Letter of recommendation_02.01.2019.pdf', 'rb')
pdf4File = open('WindTechCertificate.pdf', 'rb')
pdf5File = open('Bachelor of Engineering Certificate.pdf', 'rb')
pdf6File = open('DD214noSocialSecFirstpage.pdf', 'rb')

pdf1Reader = PyPDF2.PdfFileReader(pdf1File)
pdf2Reader = PyPDF2.PdfFileReader(pdf2File)
pdf3Reader = PyPDF2.PdfFileReader(pdf3File)
pdf4Reader = PyPDF2.PdfFileReader(pdf4File)
pdf5Reader = PyPDF2.PdfFileReader(pdf5File)
pdf6Reader = PyPDF2.PdfFileReader(pdf6File)

pdfWriter = PyPDF2.PdfFileWriter()

for pageNum in range(pdf1Reader.numPages):
	pageObj = pdf1Reader.getPage(pageNum)
	pdfWriter.addPage(pageObj)

for pageNum in range(pdf2Reader.numPages):
	pageObj = pdf2Reader.getPage(pageNum)
	pdfWriter.addPage(pageObj)

for pageNum in range(pdf3Reader.numPages):
	pageObj = pdf3Reader.getPage(pageNum)
	pdfWriter.addPage(pageObj)

for pageNum in range(pdf4Reader.numPages):
	pageObj = pdf4Reader.getPage(pageNum)
	pdfWriter.addPage(pageObj)

for pageNum in range(pdf5Reader.numPages):
	pageObj = pdf5Reader.getPage(pageNum)
	pdfWriter.addPage(pageObj)

for pageNum in range(pdf6Reader.numPages):
	pageObj = pdf6Reader.getPage(pageNum)
	pdfWriter.addPage(pageObj)

pdfOutputFile = open('combinedAppl.pdf', 'wb')
pdfWriter.write(pdfOutputFile)
pdfOutputFile.close()
pdf1File.close()
pdf2File.close()
pdf3File.close()
pdf4File.close()
pdf5File.close()
pdf6File.close()
