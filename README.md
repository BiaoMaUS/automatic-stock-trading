# automatic-stock-trading
this is a stock trading software
public class Bar {
	private Date date;
	private float open, high, low, close, AdjClose;
	private long  volume;
	
	//constructors
	public Bar() {
		date = new Date();
		open= high= low= close= AdjClose = 0.0f;
		volume = 0;
	}
	public Bar(Date d, float o, float h, float l, float c, long v, float ac){
		date = new Date(d);
		open= o;
		high= h;
		low= l;
		close= c;
		AdjClose = ac;
		volume = v;
	}
	public Bar(String d, float o, float h, float l, float c, long v, float ac){
		date = new Date(d);
		open= o;
		high= h;
		low= l;
		close= c;
		AdjClose = ac;
		volume = v;
	}
	public Bar(String line) {
		String [] Data = line.split(",");
		if (Data.length != 7) {
			System.err.println("Corrupt data!!");
			return;
		}
		date = new Date(Data[0]);
		open = Float.parseFloat(Data[1]);
		high = Float.parseFloat(Data[2]);
		low  = Float.parseFloat(Data[3]);
		close = Float.parseFloat(Data[4]);
		AdjClose = Float.parseFloat(Data[6]);
		volume = Long.parseLong(Data[5]);
	}
	
	//accessors 
	public Date date() {
		return date;
	}
	public float open() {
		return open;
	}
	public float high() {
		return high;
	}
	public float low() {
		return low;
	}
	public float close() {
		return close;
	}
	public float AdjClose() {
		return AdjClose;
	}
	public long volume() {
		return volume;
	}
	//mutators
	public void setOpen(float o) {
		open = o;
	}
	public void setHigh(float c) {
		high = c;
	}
	public void setLow(float c) {
		low = c;
	}
	public void setClose(float c) {
		close = c;
	}
	public void setAdjClose(float c) {
		AdjClose = c;
	}
	public void setVolume(long c) {
		volume = c;
	}
	//method that returns the range
	public float range() {
		return (high - low);
	}
}
