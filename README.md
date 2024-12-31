//
//  ContentView.swift
//  Memorize
//
//  Created by Sheraz Ahmad on 31/12/2024.
//

import SwiftUI

struct ContentView: View {
    let emojis = ["👻","💀","☠️","👽","👻","💀","☠️","👽"]
    let cardCount : Int = 8
    var body: some View {
        HStack() {
            ForEach(0..<cardCount , id: \.self){ index in
                CardView(content: emojis[index])
            }
        }
        .foregroundColor(.orange)
        .padding()
    }
}

struct CardView: View{
    let content: String
    @State var isFaceUp = true
    var body: some View{
        ZStack{
            let base = RoundedRectangle(cornerRadius: 12)
            if isFaceUp{
                    base.fill(.white)
                    base.strokeBorder(lineWidth: 2)
                Text(content).font(.largeTitle)
            }
            else{
                base.fill()
            }
        }
        .onTapGesture {
            isFaceUp.toggle()
        }
    }
}







struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
                
