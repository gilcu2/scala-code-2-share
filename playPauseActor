
// Play and Pause akka actor
object PlayActor {
  case class Play()
  case class Pause()
  private case class RunStep()
}

abstract  class PlayActor extends Actor {
  def run()
  var running=false
  def receive = {
    case Play => {
      running=true
      println("Running")
      self ! RunStep
    }
    case RunStep if( running)=>  {
        //println("Computing")
        run
        self ! RunStep
    }
    case Pause=> {
      running=false
      println("Pause running")
    }
  }
}
