# KeVLTechProject1
//
//  ViewController7.swift
//  KeVLTech
//
//  Created by Kevin Lau on 2/9/2017.
//  Copyright © 2017 KeVLTech. All rights reserved.
//

import UIKit
import AVFoundation

class ViewController7: UIViewController {
    
    var audioPlayer = AVAudioPlayer()
    
    @IBAction func back3(_ sender: Any) {
    }
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view, typically from a nib.
        do{
            audioPlayer = try AVAudioPlayer(contentsOf: URL.init(fileURLWithPath: Bundle.main.path(forResource: "8bit", ofType: "mp3")!))
            audioPlayer.prepareToPlay()
            
            let audioSession = AVAudioSession.sharedInstance()
            do{
                try audioSession.setCategory(AVAudioSessionCategoryPlayback)
                
            }
            catch {
                
            }
        }
        catch{
            print(error)
        }
    }
    
    override func didReceiveMemoryWarning() {
        super.didReceiveMemoryWarning()
        // Dispose of any resources that can be recreated.
    }
    
    
    
    @IBAction func musicplay(_ sender: Any) {
        audioPlayer.play()
    }
    
    
   
    @IBAction func musicpause(_ sender: Any) {
        if audioPlayer.isPlaying {
            audioPlayer.pause()
        }else {
            
        }
    }
    
    
    @IBAction func musicrestart(_ sender: Any) {
        
        if audioPlayer.isPlaying {
            audioPlayer.currentTime = 0
            audioPlayer.play()
        }else {
            audioPlayer.play()
        }
    }
    
    
}
