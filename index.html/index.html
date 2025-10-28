import React, { useState, useEffect } from 'react';
import { Calendar, Target, BookOpen, Award, Sparkles, MessageCircle, TrendingUp, CheckCircle, Circle, Plus, X, Edit2, Trash2, ChevronDown, ChevronRight, BarChart3, Image as ImageIcon } from 'lucide-react';

const CATEGORIES = [
  { id: 'learning', name: '📚 학습 활동', icon: BookOpen, color: 'bg-blue-500' },
  { id: 'awards', name: '🏆 수상/인증', icon: Award, color: 'bg-yellow-500' },
  { id: 'activities', name: '🎨 특별 활동', icon: Sparkles, color: 'bg-purple-500' },
  { id: 'daily', name: '💭 일상 & 생각', icon: MessageCircle, color: 'bg-green-500' },
  { id: 'goals', name: '🎯 목표 & 계획', icon: Target, color: 'bg-red-500' }
];

const GOAL_PERIODS = ['일일', '주간', '월간', '분기', '연간'];

export default function MagicDiary() {
  const [currentTab, setCurrentTab] = useState('dashboard');
  const [entries, setEntries] = useState([]);
  const [habits, setHabits] = useState([]);
  const [goals, setGoals] = useState([]);
  const [habitChecks, setHabitChecks] = useState({});
  const [loading, setLoading] = useState(true);
  const [showEntryModal, setShowEntryModal] = useState(false);
  const [showHabitModal, setShowHabitModal] = useState(false);
  const [showGoalModal, setShowGoalModal] = useState(false);
  const [editingEntry, setEditingEntry] = useState(null);
  const [editingHabit, setEditingHabit] = useState(null);
  const [editingGoal, setEditingGoal] = useState(null);

  useEffect(() => {
    loadData();
  }, []);

  const loadData = async () => {
    try {
      const [entriesRes, habitsRes, goalsRes, checksRes] = await Promise.all([
        window.storage.get('diary-entries').catch(() => null),
        window.storage.get('diary-habits').catch(() => null),
        window.storage.get('diary-goals').catch(() => null),
        window.storage.get('diary-checks').catch(() => null)
      ]);

      if (entriesRes) setEntries(JSON.parse(entriesRes.value));
      if (habitsRes) setHabits(JSON.parse(habitsRes.value));
      if (goalsRes) setGoals(JSON.parse(goalsRes.value));
      if (checksRes) setHabitChecks(JSON.parse(checksRes.value));
    } catch (error) {
      console.error('데이터 로딩 실패:', error);
    } finally {
      setLoading(false);
    }
  };

  const saveEntries = async (newEntries) => {
    setEntries(newEntries);
    await window.storage.set('diary-entries', JSON.stringify(newEntries));
  };

  const saveHabits = async (newHabits) => {
    setHabits(newHabits);
    await window.storage.set('diary-habits', JSON.stringify(newHabits));
  };

  const saveGoals = async (newGoals) => {
    setGoals(newGoals);
    await window.storage.set('diary-goals', JSON.stringify(newGoals));
  };

  const saveChecks = async (newChecks) => {
    setHabitChecks(newChecks);
    await window.storage.set('diary-checks', JSON.stringify(newChecks));
  };

  const toggleHabitCheck = async (habitId) => {
    const today = new Date().toISOString().split('T')[0];
    const key = `${habitId}-${today}`;
    const newChecks = { ...habitChecks, [key]: !habitChecks[key] };
    await saveChecks(newChecks);
  };

  const getHabitStreak = (habitId) => {
    let streak = 0;
    const today = new Date();
    
    for (let i = 0; i < 365; i++) {
      const date = new Date(today);
      date.setDate(date.getDate() - i);
      const dateStr = date.toISOString().split('T')[0];
      const key = `${habitId}-${dateStr}`;
      
      if (habitChecks[key]) {
        streak++;
      } else if (i > 0) {
        break;
      }
    }
    return streak;
  };

  const getCompletionRate = (period = 'week') => {
    const today = new Date();
    let days = 7;
    if (period === 'month') days = 30;
    if (period === 'year') days = 365;

    let totalChecks = 0;
    let possibleChecks = habits.length * days;

    for (let i = 0; i < days; i++) {
      const date = new Date(today);
      date.setDate(date.getDate() - i);
      const dateStr = date.toISOString().split('T')[0];
      
      habits.forEach(habit => {
        const key = `${habit.id}-${dateStr}`;
        if (habitChecks[key]) totalChecks++;
      });
    }

    return possibleChecks > 0 ? Math.round((totalChecks / possibleChecks) * 100) : 0;
  };

  const getTodayCompletionRate = () => {
    if (habits.length === 0) return 0;
    const today = new Date().toISOString().split('T')[0];
    const completed = habits.filter(habit => habitChecks[`${habit.id}-${today}`]).length;
    return Math.round((completed / habits.length) * 100);
  };

  const Dashboard = () => {
    const todayRate = getTodayCompletionRate();
    const weekRate = getCompletionRate('week');
    const monthRate = getCompletionRate('month');
    const today = new Date().toISOString().split('T')[0];
    const recentEntries = [...entries].sort((a, b) => new Date(b.date) - new Date(a.date)).slice(0, 5);

    return (
      <div className="space-y-6">
        <div className="bg-gradient-to-r from-purple-500 to-pink-500 rounded-lg p-6 text-white">
          <h2 className="text-2xl font-bold mb-2">✨ 오늘도 꿈을 향해!</h2>
          <p className="text-purple-100">당신의 노력이 마법이 됩니다</p>
        </div>

        <div className="grid grid-cols-3 gap-4">
          <div className="bg-white rounded-lg p-4 shadow">
            <div className="text-sm text-gray-600 mb-1">오늘</div>
            <div className="text-3xl font-bold text-blue-600">{todayRate}%</div>
          </div>
          <div className="bg-white rounded-lg p-4 shadow">
            <div className="text-sm text-gray-600 mb-1">이번 주</div>
            <div className="text-3xl font-bold text-green-600">{weekRate}%</div>
          </div>
          <div className="bg-white rounded-lg p-4 shadow">
            <div className="text-sm text-gray-600 mb-1">이번 달</div>
            <div className="text-3xl font-bold text-purple-600">{monthRate}%</div>
          </div>
        </div>

        <div className="bg-white rounded-lg p-6 shadow">
          <h3 className="font-bold text-lg mb-4">📝 오늘의 학습 습관</h3>
          {habits.length === 0 ? (
            <p className="text-gray-500">아직 등록된 학습 습관이 없어요</p>
          ) : (
            <div className="space-y-3">
              {habits.map(habit => (
                <div key={habit.id} className="flex items-center justify-between p-3 bg-gray-50 rounded-lg">
                  <div className="flex items-center gap-3">
                    <button
                      onClick={() => toggleHabitCheck(habit.id)}
                      className="w-6 h-6 flex items-center justify-center"
                    >
                      {habitChecks[`${habit.id}-${today}`] ? (
                        <CheckCircle className="w-6 h-6 text-green-500" />
                      ) : (
                        <Circle className="w-6 h-6 text-gray-300" />
                      )}
                    </button>
                    <span className={habitChecks[`${habit.id}-${today}`] ? 'line-through text-gray-400' : ''}>
                      {habit.name}
                    </span>
                  </div>
                  <div className="text-sm text-gray-600">
                    🔥 {getHabitStreak(habit.id)}일 연속
                  </div>
                </div>
              ))}
            </div>
          )}
        </div>

        <div className="bg-white rounded-lg p-6 shadow">
          <h3 className="font-bold text-lg mb-4">🎯 진행 중인 목표</h3>
          {goals.length === 0 ? (
            <p className="text-gray-500">목표를 설정해보세요!</p>
          ) : (
            <div className="space-y-2">
              {goals.filter(g => g.status !== 'completed').slice(0, 5).map(goal => (
                <div key={goal.id} className="p-3 bg-gray-50 rounded-lg">
                  <div className="flex items-center justify-between">
                    <span className="font-medium">{goal.title}</span>
                    <span className="text-xs text-gray-500">{goal.period}</span>
                  </div>
                </div>
              ))}
            </div>
          )}
        </div>

        <div className="bg-white rounded-lg p-6 shadow">
          <h3 className="font-bold text-lg mb-4">📅 최근 활동</h3>
          {recentEntries.length === 0 ? (
            <p className="text-gray-500">아직 기록이 없어요</p>
          ) : (
            <div className="space-y-3">
              {recentEntries.map(entry => {
                const category = CATEGORIES.find(c => c.id === entry.category);
                return (
                  <div key={entry.id} className="p-3 bg-gray-50 rounded-lg">
                    <div className="flex items-center gap-2 mb-1">
                      <span className="text-sm">{category?.name.split(' ')[0]}</span>
                      <span className="text-xs text-gray-500">{entry.date}</span>
                    </div>
                    <div className="font-medium">{entry.title}</div>
                  </div>
                );
              })}
            </div>
          )}
        </div>
      </div>
    );
  };

  const HabitsView = () => {
    return (
      <div className="space-y-6">
        <div className="flex justify-between items-center">
          <h2 className="text-2xl font-bold">📝 학습 습관 관리</h2>
          <button
            onClick={() => setShowHabitModal(true)}
            className="bg-blue-500 text-white px-4 py-2 rounded-lg flex items-center gap-2 hover:bg-blue-600"
          >
            <Plus className="w-4 h-4" /> 습관 추가
          </button>
        </div>

        <div className="grid grid-cols-3 gap-4">
          <div className="bg-white rounded-lg p-4 shadow">
            <div className="text-sm text-gray-600 mb-1">오늘 완주율</div>
            <div className="text-3xl font-bold text-blue-600">{getTodayCompletionRate()}%</div>
          </div>
          <div className="bg-white rounded-lg p-4 shadow">
            <div className="text-sm text-gray-600 mb-1">주간 완주율</div>
            <div className="text-3xl font-bold text-green-600">{getCompletionRate('week')}%</div>
          </div>
          <div className="bg-white rounded-lg p-4 shadow">
            <div className="text-sm text-gray-600 mb-1">월간 완주율</div>
            <div className="text-3xl font-bold text-purple-600">{getCompletionRate('month')}%</div>
          </div>
        </div>

        <div className="bg-white rounded-lg p-6 shadow">
          {habits.length === 0 ? (
            <div className="text-center py-12 text-gray-500">
              <p className="mb-2">아직 등록된 학습 습관이 없어요</p>
              <p className="text-sm">매일 실천할 학습 습관을 추가해보세요!</p>
            </div>
          ) : (
            <div className="space-y-4">
              {habits.map(habit => {
                const today = new Date().toISOString().split('T')[0];
                const streak = getHabitStreak(habit.id);
                
                return (
                  <div key={habit.id} className="p-4 bg-gray-50 rounded-lg">
                    <div className="flex items-center justify-between mb-3">
                      <div className="flex items-center gap-3 flex-1">
                        <button
                          onClick={() => toggleHabitCheck(habit.id)}
                          className="w-8 h-8 flex items-center justify-center"
                        >
                          {habitChecks[`${habit.id}-${today}`] ? (
                            <CheckCircle className="w-8 h-8 text-green-500" />
                          ) : (
                            <Circle className="w-8 h-8 text-gray-300" />
                          )}
                        </button>
                        <div className="flex-1">
                          <div className="font-medium text-lg">{habit.name}</div>
                          {habit.description && (
                            <div className="text-sm text-gray-600">{habit.description}</div>
                          )}
                        </div>
                      </div>
                      <div className="flex items-center gap-2">
                        <button
                          onClick={() => {
                            setEditingHabit(habit);
                            setShowHabitModal(true);
                          }}
                          className="p-2 hover:bg-gray-200 rounded"
                        >
                          <Edit2 className="w-4 h-4 text-gray-600" />
                        </button>
                        <button
                          onClick={async () => {
                            if (confirm('이 습관을 삭제하시겠습니까?')) {
                              await saveHabits(habits.filter(h => h.id !== habit.id));
                            }
                          }}
                          className="p-2 hover:bg-gray-200 rounded"
                        >
                          <Trash2 className="w-4 h-4 text-red-500" />
                        </button>
                      </div>
                    </div>
                    <div className="flex items-center gap-4 text-sm text-gray-600">
                      <span>🔥 연속 {streak}일</span>
                      <span>📅 주간 완주율: {getHabitWeekRate(habit.id)}%</span>
                    </div>
                  </div>
                );
              })}
            </div>
          )}
        </div>
      </div>
    );
  };

  const getHabitWeekRate = (habitId) => {
    let completed = 0;
    const today = new Date();
    
    for (let i = 0; i < 7; i++) {
      const date = new Date(today);
      date.setDate(date.getDate() - i);
      const dateStr = date.toISOString().split('T')[0];
      const key = `${habitId}-${dateStr}`;
      if (habitChecks[key]) completed++;
    }
    
    return Math.round((completed / 7) * 100);
  };

  const GoalsView = () => {
    const [expandedGoals, setExpandedGoals] = useState({});

    const toggleExpand = (goalId) => {
      setExpandedGoals(prev => ({ ...prev, [goalId]: !prev[goalId] }));
    };

    const groupedGoals = GOAL_PERIODS.reduce((acc, period) => {
      acc[period] = goals.filter(g => g.period === period);
      return acc;
    }, {});

    return (
      <div className="space-y-6">
        <div className="flex justify-between items-center">
          <h2 className="text-2xl font-bold">🎯 목표 관리</h2>
          <button
            onClick={() => setShowGoalModal(true)}
            className="bg-blue-500 text-white px-4 py-2 rounded-lg flex items-center gap-2 hover:bg-blue-600"
          >
            <Plus className="w-4 h-4" /> 목표 추가
          </button>
        </div>

        {goals.length === 0 ? (
          <div className="bg-white rounded-lg p-12 shadow text-center text-gray-500">
            <p className="mb-2">아직 설정된 목표가 없어요</p>
            <p className="text-sm">장기 목표와 실천 계획을 세워보세요!</p>
          </div>
        ) : (
          <div className="space-y-6">
            {GOAL_PERIODS.map(period => {
              const periodGoals = groupedGoals[period];
              if (periodGoals.length === 0) return null;

              return (
                <div key={period} className="bg-white rounded-lg p-6 shadow">
                  <h3 className="font-bold text-lg mb-4">{period} 목표</h3>
                  <div className="space-y-3">
                    {periodGoals.map(goal => (
                      <div key={goal.id} className="border rounded-lg p-4">
                        <div className="flex items-start justify-between">
                          <div className="flex-1">
                            <div className="flex items-center gap-2 mb-2">
                              <button
                                onClick={() => toggleExpand(goal.id)}
                                className="p-1 hover:bg-gray-100 rounded"
                              >
                                {expandedGoals[goal.id] ? (
                                  <ChevronDown className="w-4 h-4" />
                                ) : (
                                  <ChevronRight className="w-4 h-4" />
                                )}
                              </button>
                              <span className="font-medium text-lg">{goal.title}</span>
                              {goal.status === 'completed' && (
                                <span className="bg-green-100 text-green-700 text-xs px-2 py-1 rounded">완료</span>
                              )}
                            </div>
                            {expandedGoals[goal.id] && (
                              <div className="ml-8 space-y-2">
                                {goal.description && (
                                  <p className="text-gray-600 text-sm">{goal.description}</p>
                                )}
                                {goal.startDate && (
                                  <p className="text-sm text-gray-500">
                                    📅 {goal.startDate} ~ {goal.endDate || '진행중'}
                                  </p>
                                )}
                              </div>
                            )}
                          </div>
                          <div className="flex items-center gap-2">
                            <button
                              onClick={() => {
                                setEditingGoal(goal);
                                setShowGoalModal(true);
                              }}
                              className="p-2 hover:bg-gray-100 rounded"
                            >
                              <Edit2 className="w-4 h-4 text-gray-600" />
                            </button>
                            <button
                              onClick={async () => {
                                if (confirm('이 목표를 삭제하시겠습니까?')) {
                                  await saveGoals(goals.filter(g => g.id !== goal.id));
                                }
                              }}
                              className="p-2 hover:bg-gray-100 rounded"
                            >
                              <Trash2 className="w-4 h-4 text-red-500" />
                            </button>
                          </div>
                        </div>
                      </div>
                    ))}
                  </div>
                </div>
              );
            })}
          </div>
        )}
      </div>
    );
  };

  const PortfolioView = () => {
    const [selectedCategory, setSelectedCategory] = useState('all');
    const filteredEntries = selectedCategory === 'all' 
      ? entries 
      : entries.filter(e => e.category === selectedCategory);
    
    const sortedEntries = [...filteredEntries].sort((a, b) => new Date(b.date) - new Date(a.date));

    return (
      <div className="space-y-6">
        <div className="flex justify-between items-center">
          <h2 className="text-2xl font-bold">📚 포트폴리오</h2>
          <button
            onClick={() => setShowEntryModal(true)}
            className="bg-blue-500 text-white px-4 py-2 rounded-lg flex items-center gap-2 hover:bg-blue-600"
          >
            <Plus className="w-4 h-4" /> 기록 추가
          </button>
        </div>

        <div className="flex gap-2 flex-wrap">
          <button
            onClick={() => setSelectedCategory('all')}
            className={`px-4 py-2 rounded-lg ${selectedCategory === 'all' ? 'bg-blue-500 text-white' : 'bg-gray-200'}`}
          >
            전체
          </button>
          {CATEGORIES.map(cat => (
            <button
              key={cat.id}
              onClick={() => setSelectedCategory(cat.id)}
              className={`px-4 py-2 rounded-lg ${selectedCategory === cat.id ? 'bg-blue-500 text-white' : 'bg-gray-200'}`}
            >
              {cat.name}
            </button>
          ))}
        </div>

        {sortedEntries.length === 0 ? (
          <div className="bg-white rounded-lg p-12 shadow text-center text-gray-500">
            <p className="mb-2">아직 기록이 없어요</p>
            <p className="text-sm">특별한 경험과 활동을 기록해보세요!</p>
          </div>
        ) : (
          <div className="space-y-4">
            {sortedEntries.map(entry => {
              const category = CATEGORIES.find(c => c.id === entry.category);
              return (
                <div key={entry.id} className="bg-white rounded-lg p-6 shadow">
                  <div className="flex items-start justify-between mb-3">
                    <div className="flex-1">
                      <div className="flex items-center gap-2 mb-2">
                        <span className={`${category?.color} text-white px-2 py-1 rounded text-sm`}>
                          {category?.name.split(' ')[0]}
                        </span>
                        <span className="text-sm text-gray-500">{entry.date}</span>
                      </div>
                      <h3 className="text-xl font-bold mb-2">{entry.title}</h3>
                      <p className="text-gray-700 whitespace-pre-wrap">{entry.content}</p>
                      {entry.imageUrl && (
                        <div className="mt-4">
                          <img 
                            src={entry.imageUrl} 
                            alt={entry.title}
                            className="max-w-md rounded-lg"
                            onError={(e) => {
                              e.target.style.display = 'none';
                            }}
                          />
                        </div>
                      )}
                    </div>
                    <div className="flex items-center gap-2 ml-4">
                      <button
                        onClick={() => {
                          setEditingEntry(entry);
                          setShowEntryModal(true);
                        }}
                        className="p-2 hover:bg-gray-100 rounded"
                      >
                        <Edit2 className="w-4 h-4 text-gray-600" />
                      </button>
                      <button
                        onClick={async () => {
                          if (confirm('이 기록을 삭제하시겠습니까?')) {
                            await saveEntries(entries.filter(e => e.id !== entry.id));
                          }
                        }}
                        className="p-2 hover:bg-gray-100 rounded"
                      >
                        <Trash2 className="w-4 h-4 text-red-500" />
                      </button>
                    </div>
                  </div>
                </div>
              );
            })}
          </div>
        )}
      </div>
    );
  };

  const EntryModal = () => {
    const [formData, setFormData] = useState(editingEntry || {
      title: '',
      content: '',
      category: 'learning',
      date: new Date().toISOString().split('T')[0],
      imageUrl: ''
    });

    const handleSubmit = async (e) => {
      e.preventDefault();
      
      if (editingEntry) {
        await saveEntries(entries.map(entry => 
          entry.id === editingEntry.id ? { ...formData, id: entry.id } : entry
        ));
      } else {
        await saveEntries([...entries, { ...formData, id: Date.now().toString() }]);
      }
      
      setShowEntryModal(false);
      setEditingEntry(null);
    };

    return (
      <div className="fixed inset-0 bg-black bg-opacity-50 flex items-center justify-center p-4 z-50">
        <div className="bg-white rounded-lg p-6 max-w-2xl w-full max-h-[90vh] overflow-y-auto">
          <div className="flex justify-between items-center mb-4">
            <h3 className="text-xl font-bold">{editingEntry ? '기록 수정' : '새 기록 추가'}</h3>
            <button onClick={() => { setShowEntryModal(false); setEditingEntry(null); }}>
              <X className="w-6 h-6" />
            </button>
          </div>
          
          <form onSubmit={handleSubmit} className="space-y-4">
            <div>
              <label className="block text-sm font-medium mb-1">카테고리</label>
              <select
                value={formData.category}
                onChange={(e) => setFormData({ ...formData, category: e.target.value })}
                className="w-full border rounded-lg p-2"
                required
              >
                {CATEGORIES.map(cat => (
                  <option key={cat.id} value={cat.id}>{cat.name}</option>
                ))}
              </select>
            </div>
            
            <div>
              <label className="block text-sm font-medium mb-1">날짜</label>
              <input
                type="date"
                value={formData.date}
                onChange={(e) => setFormData({ ...formData, date: e.target.value })}
                className="w-full border rounded-lg p-2"
                required
              />
            </div>
            
            <div>
              <label className="block text-sm font-medium mb-1">제목</label>
              <input
                type="text"
                value={formData.title}
                onChange={(e) => setFormData({ ...formData, title: e.target.value })}
                className="w-full border rounded-lg p-2"
                placeholder="제목을 입력하세요"
                required
              />
            </div>
            
            <div>
              <label className="block text-sm font-medium mb-1">내용</label>
              <textarea
                value={formData.content}
                onChange={(e) => setFormData({ ...formData, content: e.target.value })}
                className="w-full border rounded-lg p-2 h-32"
                placeholder="내용을 입력하세요"
                required
              />
            </div>
            
            <div>
              <label className="block text-sm font-medium mb-1">
                <div className="flex items-center gap-2">
                  <ImageIcon className="w-4 h-4" />
                  이미지 URL (선택)
                </div>
              </label>
              <input
                type="url"
                value={formData.imageUrl}
                onChange={(e) => setFormData({ ...formData, imageUrl: e.target.value })}
                className="w-full border rounded-lg p-2"
                placeholder="https://example.com/image.jpg"
              />
              <p className="text-xs text-gray-500 mt-1">구글 포토 공유 링크 등을 붙여넣으세요</p>
            </div>
            
            <div className="flex gap-2">
              <button
                type="submit"
                className="flex-1 bg-blue-500 text-white py-2 rounded-lg hover:bg-blue-600"
              >
                {editingEntry ? '수정하기' : '추가하기'}
              </button>
              <button