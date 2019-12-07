import java.lang.Exception
import java.lang.NumberFormatException
import java.util.*
import kotlin.random.Random

fun main(){
    val et = ExceptionTester()
    val sc = Scanner(System.`in`)
    val gottaGuess = Random.nextInt(0,100)
    var guessedNumber = 101

    var tryCounter = 0
    println("ჩავიფიქრე რიცხვი.. ახლა გამოიცანი")
    while (true){
//NumberFormatException example
        try {//ვცადოთ მომხმარებლის Input-ის აღება და ინტ-ად გადაქცევა
            guessedNumber = sc.nextLine().toInt()
        }catch (ime: NumberFormatException){//თუ რიცხვი არ შემოვიდა, მთელი while დავსკიპოთ და გავაფრთხილოთ მომხმარებელი
            println("უნდა შემოიტანოთ მხოლოდ და მხოლოდ რიცხვი! სცადეთ თავიდან!")
            continue
        }
//custom exception example
        try {  //ვცადოთ შემოტანილი რიცხვის ჩასმა ფუნქციაში, რომელიც ტესტავს საზღვრებს ცდება თუ არა ის
            et.numberOutOfBounds(guessedNumber)
        }catch (e: NumberOutOfBounds){ //თუ მოხდა ჩვენ მიერ შექმნილი NumberOutOfBounds შექმნილი Exceptionის დაჭერა, მაშინ დაპრინტოს მისი მესიჯი და while loop-ის ერთი იტერაცია გამოიტოვოს
            println(e)
            continue
        }

        tryCounter+=1
        if(guessedNumber < gottaGuess){
            println("ჩემი ჩაფიქრებული რიცხვი უფრო დიდია... [მცდელობა: $tryCounter]")
        }
        if(guessedNumber > gottaGuess){
            println("ჩემი ჩაფიქრებული რიცხვი უფრო პატარაა... [მცდელობა: $tryCounter]")
        }
        if(guessedNumber == gottaGuess){
            println("ყოჩაღ! მე $gottaGuess ჩავიფიქრე. სულ დაგჭირდა $tryCounter მცდელობა.")
            break;
        }
    }
}

class NumberOutOfBounds(message: String) : Exception(message) //ვაკეთებთ Exception-ის მემკვიდრე კლასს საკუთარი Exception -ის შესაქმნელად

class ExceptionTester() { //ვაკეთებთ კლასს სადაც გავტესტავთ შემოტანილ რიცხვს და თუ ის ცდება საზღვრებს ვისვრით Exception-ს
    fun numberOutOfBounds(number: Int){
        if(number > 100 || number < 0) {
            throw NumberOutOfBounds("აქ რიცხვი აცდენილია 0-დან 100-მდე საზღვრებს. შეიტანეთ რიცხვი სწორად!! ")
        }
    }
}
