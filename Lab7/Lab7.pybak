# Lab 7 
# Colin Reed

# *********** LAB 4 ***********

def simpleCopy(pic):
  w = getWidth(pic)
  h = getHeight(pic)
  copyPic = makeEmptyPicture(w,h)
  copyPixels = getPixels(copyPic)
  picPixels = getPixels(pic)
  iterator = -1 # negative val because ++ occurs before call
  for i in picPixels:
    iterator += 1
    readColor = getColor(i) #IT's already isolating. 
    setColor(copyPixels[iterator], readColor)
  show(copyPic)
  return copyPic
  
def shrink(pic):
  wi = getWidth(pic)
  hi = getHeight(pic)
  wf = wi/2
  hf = hi/2
  smallPic = makeEmptyPicture(wf,hf)
  smallPixels = getPixels(smallPic)
  for i in range(0, wi, 2):
    for j in range(0, hi, 2):
      readColor = getColor(getPixel(pic, i, j))
      writePixel = getPixel(smallPic, (i/2) , (j/2))
      setColor(writePixel, readColor)
  return smallPic
  
# ********** LAB 5 **********
def pyCopy(source, target, targetX, targetY):
  wi = getWidth(source)
  hi = getHeight(source)
  for i in range(0, wi):
    for j in range(0,hi):
      readColor = getColor(getPixel(source, i, j))
      writePixel = getPixel(target, i+targetX, j+targetY)
      setColor(writePixel,readColor)
  return target
  
# *********** LAB 6 ***********
def chromakey(greenpic,pic):
  for x in range(0, getWidth(greenpic)):
    for y in range(0, getHeight(greenpic)):
      p = getPixel(greenpic, x, y)
      g = getGreen(p)
      if distance(getColor(p), white) < 100.0:
        setColor(p, getColor(getPixel(pic, x, y)))
  return greenpic

# *********** LAB 7 ***********
def makeCard(gold,con, ground):
  h = getHeight(ground)
  w = getWidth(ground)
  
  gold = shrink(gold)
  ground = chromakey(gold,ground)
  
  #ground = pyCopy(con, ground, (w-getWidth(con)), (h-getHeight(con)))
  #ground = pyCopy(gold, ground, 0 , (h-getHeight(gold)))
  
  customText = makeStyle( sansSerif, bold , 70)
  addTextWithStyle(ground, 55, 60, "Happy St. Patrick's Day",customText)
  
  return ground


# ********** Lab running code **********

#Replace with file path hard coding 
# Gold 
file1 = pickAFile()
pic1 = makePicture(file1)
# Con 
file2 = pickAFile()
pic2 = makePicture(file2)
# Ground
file3 = pickAFile()
pic3 = makePicture(file3)
result = makeCard(pic1, pic2, pic3)
writePictureTo(result,'//home//colin//Downloads//card.jpg')