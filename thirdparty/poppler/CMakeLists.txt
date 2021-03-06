
add_library(poppler STATIC
      poppler/Annot.cc
      poppler/Array.cc
      poppler/BuiltinFont.cc
      poppler/BuiltinFontTables.cc
      poppler/CachedFile.cc
	#poppler/CairoFontEngine.cc
	#poppler/CairoOutputDev.cc
	#poppler/CairoRescaleBox.cc
      poppler/Catalog.cc
      poppler/CharCodeToUnicode.cc
      poppler/CMap.cc
	#poppler/CurlCachedFile.cc
	#poppler/CurlPDFDocBuilder.cc
      poppler/DateInfo.cc
	#poppler/DCTStream.cc
      poppler/Decrypt.cc
      poppler/Dict.cc
      poppler/Error.cc
      poppler/FileSpec.cc
	#poppler/FlateStream.cc
      poppler/FontEncodingTables.cc
      poppler/Form.cc
      poppler/FontInfo.cc
      poppler/Function.cc
      poppler/Gfx.cc
      poppler/GfxFont.cc
      poppler/GfxState.cc
      poppler/GlobalParams.cc
	#poppler/GlobalParamsWin.cc
	poppler/Hints.cc
      poppler/JArithmeticDecoder.cc
      poppler/JBIG2Stream.cc
	#poppler/JPEG2000Stream.cc
      poppler/JPXStream.cc
      poppler/Lexer.cc
	poppler/Linearization.cc
      poppler/Link.cc
      poppler/LocalPDFDocBuilder.cc
	poppler/MarkedContentOutputDev.cc
      poppler/Movie.cc
      poppler/NameToCharCode.cc
      poppler/Object.cc
      poppler/OptionalContent.cc
      poppler/Outline.cc
      poppler/OutputDev.cc
      poppler/Page.cc
	poppler/PageLabelInfo.h
	poppler/PageLabelInfo.cc
      poppler/PageTransition.cc
      poppler/Parser.cc
      poppler/PDFDoc.cc
      poppler/PDFDocEncoding.cc
      poppler/PDFDocFactory.cc
      poppler/PopplerCache.cc
	poppler/PreScanOutputDev.cc
      poppler/ProfileData.cc
      poppler/PSOutputDev.cc
      poppler/PSTokenizer.cc
      poppler/Rendition.cc
	poppler/SecurityHandler.cc
	poppler/Sound.cc
	poppler/SplashOutputDev.cc
      poppler/StdinCachedFile.cc
      poppler/StdinPDFDocBuilder.cc
      poppler/Stream.cc
      poppler/strtok_r.cpp
	poppler/StructElement.cc
	poppler/StructTreeRoot.cc
	poppler/TextOutputDev.cc
      poppler/UnicodeMap.cc
      poppler/UnicodeTypeTable.cc
	poppler/UTF.cc
	poppler/ViewerPreferences.cc
      poppler/XRef.cc

      goo/FixedPoint.cc
      goo/gfile.cc
      goo/gmem.cc
      goo/gmempp.cc
      goo/GooHash.cc
      goo/GooList.cc
      goo/GooString.cc
      goo/GooTimer.cc
	goo/grandom.cc
      goo/gstrtod.cc
      goo/ImgWriter.cc
      goo/JpegWriter.cc
	goo/NetPBMWriter.cc
      #goo/PNGWriter.cc
	goo/TiffWriter.cc

      fofi/FoFiBase.cc
      fofi/FoFiEncodings.cc
	fofi/FoFiIdentifier.cc
      fofi/FoFiTrueType.cc
      fofi/FoFiType1.cc
      fofi/FoFiType1C.cc

	splash/Splash.cc
	splash/SplashBitmap.cc
	splash/SplashClip.cc
	splash/SplashFont.cc
	splash/SplashFontEngine.cc
	splash/SplashFontFile.cc
	splash/SplashFontFileID.cc
	splash/SplashFTFont.cc
	splash/SplashFTFontEngine.cc
	splash/SplashFTFontFile.cc
	splash/SplashPath.cc
	splash/SplashPattern.cc
	splash/SplashScreen.cc
	splash/SplashState.cc
	splash/SplashT1Font.cc
	splash/SplashT1FontEngine.cc
	splash/SplashT1FontFile.cc
	splash/SplashXPath.cc
	splash/SplashXPathScanner.cc
   )

set_target_properties(poppler
      PROPERTIES
      if (APPLE)
         COMPILE_FLAGS
            "-O2 -Wno-write-strings -ansi -Wnon-virtual-dtor -Woverloaded-virtual -Wno-unused-private-field -Wno-return-stack-address -Wno-shift-negative-value"
      else (APPLE)
         if (MINGW)
            COMPILE_FLAGS
               "-O2 -Wall -Wextra -Wno-write-strings -ansi -Wnon-virtual-dtor -Woverloaded-virtual -Wno-unused-parameter -Wno-missing-field-initializers -Wno-unused-but-set-variable -Wno-format"
         else (MINGW)
             COMPILE_FLAGS
                "-O2 -Wno-write-strings -ansi -Wnon-virtual-dtor -Woverloaded-virtual -Wno-unused-parameter -Wno-missing-field-initializers -Wno-unused-but-set-variable"
         endif(MINGW)
      endif(APPLE)
      )

include_directories(
      ${PROJECT_SOURCE_DIR}/thirdparty/poppler/goo
	${PROJECT_SOURCE_DIR}/thirdparty/poppler/fofi
	${PROJECT_SOURCE_DIR}/thirdparty/poppler/splash
      )
