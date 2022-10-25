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



//OnBoarding

import SwiftUI
import CoreData

struct ContentView: View
{
   
    @AppStorage("_show") var show: Bool = true
    
    var body: some View
    {
        NavigationView
        {
                                //messo qui giusto per vedere la simulazione 
       OnBoarding(show: $show)
                                
            VStack(alignment: .center)
            {
                Text("sei nell'app").fontWeight(.black).foregroundColor(Color.green).multilineTextAlignment(.center).lineLimit(60).bold().padding(.all)
            
            
            
               
                                                
            }
            .navigationTitle("Home")
        }
            .fullScreenCover(isPresented: $show, content:
            {
                OnBoarding(show: $show)
            })
            
        }
        
    }

 
struct PageView: View
{
    
    let title: String
    let subtitle: String
    let imageName: String
        
    let dismissButton: Bool
    @AppStorage("_show") var show: Bool = true
    
    //init
    var body: some View
    {
                VStack (alignment: .center)
        {
                                Image(imageName).resizable().aspectRatio(contentMode: .fit).padding()
                                
        Text(title).font(.title).multilineTextAlignment(.center).padding()
            
                                Text(subtitle).font(.body).fontWeight(.light).multilineTextAlignment(.center).padding(.horizontal).padding()
            
            if dismissButton
            {
                Button(action:
                        {
                    show.toggle()
                        }, label:
                        {
                Text("get started").bold().foregroundColor(Color.blue).frame(width: 200, height: 50).background(Color.gray)
                })
            }
        }
    }
}


    struct ContentView_Previews: PreviewProvider
    {
        static var previews: some View
        {
            ContentView()
       
        }
    }
    
    
    
    
    //struct page views
    
import Foundation
import SwiftUI

//onboarding
struct OnBoarding: View
{
    @Binding var show: Bool
    
    var body: some View
    {
        
        TabView
        {
        
            PageView(title: "Welcome to Challengy", subtitle: "Get yourself involved in this human interaction based experience! Follow the steps and jump into the ChallengY space!", imageName: "on1" , dismissButton: false)
      
            
            PageView(title: "Explore all The Challenges" , subtitle: "Tap and generate the daily challenge. If you don’t like it, don’t worry! You will be able to generate additional challenges!", imageName: "on2",  dismissButton: false)
            
            PageView(title: "Take Care Of Your Feelings", subtitle: "Take notes about your challenges! Describe your feelings in order to improve consciousness about you.", imageName: "on3", dismissButton: false)
            
            
            PageView(title: "Let's go", subtitle: "", imageName: "on2", dismissButton: true)
        }
        .tabViewStyle(PageTabViewStyle())
    }
}


