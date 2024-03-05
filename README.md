# waterfall-layout

pod 'CHTCollectionViewWaterfallLayout'

// *******************************************

func setupCollectionView(){
        
        // Create a waterfall layout
        let layout = CHTCollectionViewWaterfallLayout()
        
        // Change individual layout attributes for the spacing between cells
        layout.minimumColumnSpacing = 8.0
        layout.minimumInteritemSpacing = 8.0
        layout.sectionInset = UIEdgeInsets(top: 10, left: 10, bottom: 10, right: 10)
        
        // Collection view attributes
        collectionViewPost.alwaysBounceVertical = true
        
        // Add the waterfall layout to your collection view
        collectionViewPost.collectionViewLayout = layout
    }
// *******************************************

// CHTCollectionViewDelegateWaterfallLayout

    func collectionView(_ collectionView: UICollectionView, layout collectionViewLayout: UICollectionViewLayout, sizeForItemAt indexPath: IndexPath) -> CGSize {
        let images = self.arrImg.map { imageName in
            return UIImage(named: imageName) ?? UIImage() // Use the default UIImage() if the named image is not found
        }
        
        return images[indexPath.row].size
    }
