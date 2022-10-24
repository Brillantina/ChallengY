# ChallengY
 hi
Hi form MarcoSantopietro computer

//
//  ViewController.swift
//  Challenges
//
//  Created by Rita Marrano on 24/10/22.
//

import UIKit

class ViewController: UIViewController
{
    @IBOutlet weak var Label: UILabel!
    
    
    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view.
    }


    @IBAction func Button(_ sender: Any)
    {
        let arrayOfChallenges = ["ciao sono alessio e sono scemo", "offri un caffè a marco scemo", "ciaocciaociaociaociaociao", "danilodanilodanilodanilco", "ritaritaritaritarita"]
        
        Label.text = arrayOfChallenges.randomElement()
        
    }
}

